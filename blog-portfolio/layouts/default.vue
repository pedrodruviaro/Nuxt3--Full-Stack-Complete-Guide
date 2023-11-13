<script setup>
useHead({
    titleTemplate: "%s - Piotr Jura",
    link: [
        {
            rel: "preconnect",
            href: "https://fonts.googleapis.com",
        },
        {
            rel: "stylesheet",
            href: "https://fonts.googleapis.com/css2?family=Roboto&display=swap",
            crossorigin: "",
        },
    ],
});

useHead({
    htmlAttrs: {
        lang: "en",
    },
    link: [
        {
            rel: "icon",
            type: "image/ico",
            href: "/favicon.ico",
        },
    ],
});

const colorMode = useColorMode();

console.log(colorMode.preference);
</script>

<template>
    <div class="container mx-auto max-w-2xl px-4 gap-4">
        <header class="flex items-center justify-between gap-4 flex-wrap mt-5">
            <div>
                <NuxtLink to="/" class="text-xl font-semibold hover:bg-gray-200"
                    >Piotr Jura</NuxtLink
                >
            </div>

            <Menu />
        </header>
        <main class="pb-2 mt-10">
            <slot />
        </main>
    </div>
</template>

<style>
body {
    font-family: "Roboto", sans-serif;
}

body {
    @apply bg-white dark:bg-gray-900 text-gray-700 dark:text-gray-300;
}
</style>
