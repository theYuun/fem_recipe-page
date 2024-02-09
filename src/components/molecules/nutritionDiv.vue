<script setup>
</script>

<template>
    <div class="nutritionDivider"><slot></slot></div>
</template>

<style>
    .nutritionDivider {
        margin: 28px 0;
        margin-right: 1px;
    }

    @media (min-width: 376px) {
        .nutritionDivider {
            margin-top: 26px;
            margin-bottom: 32px;
        }
    }
</style>
