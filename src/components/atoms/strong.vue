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
    <strong>{{ props.text }}</strong>
</template>

<style>
    strong {
        line-height: 24px;
    }
</style>
