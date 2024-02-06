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
    <h3>{{ props.text }}</h3>
</template>

<style scoped>
</style>
