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

    @media (min-width: 376px) {
        .appDiv {
            max-width: 736px;
            margin: auto;
            margin-top: 123px;
            border-radius: 25px;
        }
    }
</style>
