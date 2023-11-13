<script setup>
const route = useRoute();
</script>

<template>
    <h1>Blog: {{ route?.params?.slug }}</h1>
</template>
