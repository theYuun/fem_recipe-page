<script setup>
import { ref, defineProps } from 'vue';
const props = defineProps({
    text: {
        type: String,
        required: false,
    },
    data: {
        type: Object,
        required: false,
    },
})

</script>

<template>
    <span v-if="props.text" :aria-label="`${props.text}:`">
        {{ props.text }}
    </span>
    <span v-if="props.data || !props.text">
        <slot></slot>
    </span>
</template>

<style>
    span {
        line-height: 24px;
    }
</style>
