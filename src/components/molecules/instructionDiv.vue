<script setup>
</script>

<template>
    <div class="instructionDivider"><slot></slot></div>
</template>

<style>
    .instructionDivider {
        padding: 18px 0;
    }

    @media (min-width: 376px) {
        .instructionDivider {
            margin-top: 10px;
        }
    }
</style>
