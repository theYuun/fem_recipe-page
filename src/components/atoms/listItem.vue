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
    <li>{{ props.text }}</li>
</template>

<style scoped>
</style>
