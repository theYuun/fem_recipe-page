<script setup>
</script>

<template>
    <div class="appDiv"><slot></slot></div>
</template>

<style>
    .appDiv {
        background-color: var(--colorWhite);
        width: 100%;
        overflow: hidden;
    }

    @media (min-width: 375px) {
        .appDiv {
            width: 740px;
            margin: auto;
            margin-top: 120px;
        }
    }
</style>
