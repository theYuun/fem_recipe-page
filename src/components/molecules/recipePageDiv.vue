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
        margin: 43px;
        margin-right: 35px;
        width: calc(100% - 94px);
    }
}
</style>
