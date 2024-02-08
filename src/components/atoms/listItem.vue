<script setup>
import { ref, defineProps } from 'vue';
const props = defineProps({
    text: {
        type: String,
        required: true,
    },
    isOrderedValue: {
        type: String,
        required: false,
    }
})

const orderedListBulletContent = ref(() => {
    if (props.isOrderedValue)
        return ref(props.isOrderedValue.toString());

    return '';
});



</script>

<template>
    <li :style="{ '--orderedListBulletContent': '1' }">{{ props.text }}</li>
</template>

<style scoped>
    li {
        --dotSize: 2px;
        --orderedListBulletContent: '';

        position: relative;
        list-style-type: none;
        margin-bottom: 9px;
        line-height: 23px;
    }

    li::before {
        content: var(--orderedListBulletContent);
        position: absolute;
        top: 50%;
        left: -32px;
        transform: translateY(-2px);
        width: var(--dotSize);
        height: var(--dotSize);
        border-radius: 50%;
        background-color: var(--colorDarkCharcoal);
        box-shadow: 0 0 1px 1px var(--colorDarkCharcoal);
        font-family: 'Young';
    }
</style>
