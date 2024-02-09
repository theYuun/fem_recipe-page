<script setup>
</script>

<template>
    <div class="contentDiv"><slot></slot></div>
</template>

<style>
    .contentDiv {
        margin: 36px 32px;
        margin-right: 20px;
    }
    
    @media (min-width: 376px) {
        .contentDiv {
            margin: 0;
            margin-top: 35px;
        }
    }
</style>
