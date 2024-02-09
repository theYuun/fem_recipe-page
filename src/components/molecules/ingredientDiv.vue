<script setup>
</script>

<template>
    <div class="ingredientDivider"><slot></slot></div>
</template>

<style>
    .ingredientDivider {
        padding: 18px 0;
    }

    @media (min-width: 376px) {
        .ingredientDivider {
            padding: 0;
            margin-top: 27px;
            margin-bottom: 32px;
        }
    }
</style>
