<script setup>
import { ref, defineProps } from 'vue';
const props = defineProps({
    data: {
        type: String,
        required: true,
    }
})
</script>

<template>
    <td>
        {{ props.data }}
    </td>
</template>

<style scoped>
</style>
