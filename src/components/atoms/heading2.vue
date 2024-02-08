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
    <h2>{{ props.text }}</h2>
</template>

<style>
    h2 {
        font-family: 'Young';
        font-size: 26px;
        color: var(--colorDarkCharcoal);
        letter-spacing: 1.1px;
    }
</style>
