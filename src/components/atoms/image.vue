<script setup>
import { ref, defineProps } from 'vue';
const props = defineProps({
    url: {
        type: String,
        required: true,
    },
    imageAltText: {
        type: String,
        required: true,
    }
})
</script>

<template>
    <img class="img" :src="props.url" :alt="`${props.imageAltText}.`">
</template>

<style>
    .img {
        width: calc(100% + 10px);
    }
    @media (min-width: 376px) {
        img {
            width: calc(100% + 10px);
            border-radius: 10px;
        }
    }
</style>
