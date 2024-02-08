<script setup>
import { defineProps } from 'vue';

const props = defineProps({
    width: {
        type: Number,
        required: false,
    },
    height: {
        type: Number,
        required: false,
    },
    margins: {
        type: String,
        required: false,
    }
});

const width = props.width ? (props.width.toString() + 'px') : '0';
const height = props.height ? (props.height.toString() + 'px') : '0';
const margins = props.margins ? props.margins : '0';
</script>

<template>
    <div :style="{ '--width': width, '--height': height, '--margin': margins }"></div>
</template>

<style scoped>
    div {
        --width: 0;
        --height: 0;
        --margin: 0 0 0 0;
        width: var(--width);
        height: var(--height);
        margin: var(--margin);
    }
</style>
