<script setup>
const { data, error, pending } = await useFetch(
    "https://api.github.com/users/pedrodruviaro/repos"
);

const repositories = computed(() => {
    const repositoriesWithDescription = data.value.filter(
        (repo) => repo.description
    );

    const sortedByStars = repositoriesWithDescription.sort(
        (a, b) => b.stargazers_count - a.stargazers_count
    );

    return sortedByStars;
});
</script>

<template>
    <p class="mb-10">Take a look at my GitHub projects</p>

    <p v-if="pending">Loading</p>
    <p v-else-if="error">Something went wrong, try again</p>

    <section v-else>
        <ul class="grid grid-cols-1">
            <li
                v-for="repo in repositories"
                class="border border-gray-200 rounded-sm hover:bg-gray-100 font-mono p-4"
                :key="repo.id"
            >
                <a
                    :href="repo.html_url"
                    target="_blank"
                    rel="noopener rereferrer"
                >
                    <div class="flex items-center justify-between">
                        <div class="font-semibold">
                            {{ repo.name }}
                        </div>
                        <div>{{ repo.stargazers_count }} &#9733;</div>
                    </div>

                    <p class="text-sm">
                        {{ repo.description }}
                    </p>
                </a>
            </li>
        </ul>
    </section>
</template>
