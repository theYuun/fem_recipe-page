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

<style scoped>
</style>
