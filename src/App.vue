<script setup>
import RecipePage from './components/pages/recipePage.vue';
import recipes from './components/recipes.js';
import molecules from './components/molecules/molecules';

const AppBlock = molecules.appDiv;

</script>

<template>
    <AppBlock class="app">
        <RecipePage class="recipePage" :recipe="recipes[0]" />
    </AppBlock>
</template>

<style>
</style>
