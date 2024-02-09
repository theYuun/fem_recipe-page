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
    <p>{{ props.text }}</p>
</template>

<style>
    p {
        margin-top: 24px;
        line-height: 24px;
    }
    @media (min-width: 376px) {
        p {
            margin-top: 26px;
        }
    }
</style>
