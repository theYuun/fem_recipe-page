<script setup>
</script>

<template>
    <div class="instructionDivider"><slot></slot></div>
</template>

<style scoped>
    .instructionDivider {
        margin-top: 28px;
        margin-bottom: 30px;
    }

    @media (min-width: 376px) {
        .instructionDivider {
            margin-top: 26px;
        }
    }
</style>
