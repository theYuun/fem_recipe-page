<script setup>
import { ref, defineProps } from 'vue';
const props = defineProps({
    url: {
        type: String,
        required: true,
    }
})
</script>

<template>
    <img :src="props.url">
</template>

<style scoped>
</style>
