<script setup>
</script>

<template>
    <div class="prepTimeDiv"><slot></slot></div>
</template>

<style>
    .prepTimeDiv {
        margin-top: 30px;
        padding: 24px;
        background-color: var(--colorLightGrey);
        border-radius: 10px;
    }

    @media (min-width: 376px) {
        .prepTimeDiv {
            margin-top: 32px;
            padding: 24px 27px;
            padding-bottom: 18px;
            width: calc(100% - 46px);
        }
    }
</style>
