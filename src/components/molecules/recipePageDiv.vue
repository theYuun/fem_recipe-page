<script setup>
</script>

<template>
    <div class="recipePageDiv"><slot></slot></div>
</template>

<style>
    .recipePageDiv {
        position: relative;
        width: 100%;
    }

@media (min-width: 376px) {
    .recipePageDiv {
        margin: 41px;
        width: auto;
    }
}
</style>
