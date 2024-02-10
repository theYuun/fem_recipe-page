<script setup>
import { ref, defineProps } from 'vue';
const props = defineProps({
    text: {
        type: String,
        required: true,
    }
})
</script>

<template>
    <h1 :aria-label="`${props.text}.`">{{ props.text }}</h1>
</template>

<style>
    h1 {
        font-family: 'Young';
        font-size: 35px;
        letter-spacing: 0.6px;
        line-height: 36px;
    }

    @media (min-width: 376px) {
        h1 {
            font-size: 38px;
            letter-spacing: 1px;
        }
    }
</style>
