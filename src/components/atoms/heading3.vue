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
    <h3 :aria-label="`${props.text}.`">{{ props.text }}</h3>
</template>

<style>
    h3 {
        letter-spacing: 0.5px;
    }
</style>
