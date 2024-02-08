<script setup>
</script>

<template>
    <div class="nutritionDivider"><slot></slot></div>
</template>

<style>
    .nutritionDivider {
        padding: 18px 0;
    }

    @media (min-width: 376px) {
        .nutritionDivider {
            padding: 0;
            margin-top: 26px;
            margin-bottom: 32px;
        }
    }
</style>
