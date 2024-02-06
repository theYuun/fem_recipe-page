<script setup>
import { ref, defineProps } from 'vue';
const props = defineProps({
    data: {
        type: Array,
        required: true,
    }
})
</script>

<template>
    <li>{{ `${props.data[0].substring(0,1).toUpperCase()}${props.data[0].substring(1,props.data[0].length)}: ${props.data[1]}` }}</li>
</template>

<style scoped>
</style>
