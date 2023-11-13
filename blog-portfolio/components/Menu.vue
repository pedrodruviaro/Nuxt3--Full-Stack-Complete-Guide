<template>
    <nav class="flex items-center gap-4">
        <NuxtLink to="/">Home</NuxtLink>
        <NuxtLink to="/about">About</NuxtLink>
        <NuxtLink to="/projects">Projects</NuxtLink>
        <NuxtLink to="/blog">Blog</NuxtLink>
    </nav>
</template>

<style scoped>
a {
    @apply hover:bg-gray-100 p-1 font-mono;
}
</style>
