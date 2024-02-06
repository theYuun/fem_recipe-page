<script setup>
import RecipePage from './components/pages/recipePage.vue';
import recipes from './components/recipes.js';
</script>

<template>
    <RecipePage :recipe="recipes[0]" />
</template>

<style scoped>
</style>
