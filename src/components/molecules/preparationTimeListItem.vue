<script setup>
import { ref, defineProps } from 'vue';
import atoms from '../atoms/atoms';

const props = defineProps({
    data: {
        type: Array,
        required: true,
    },
})

const Span = atoms.span;
const Strong = atoms.strong;

</script>

<template>
    <li class="prepTimeLi">
        <Strong :text="`${props.data[0].substring(0,1).toUpperCase()}${props.data[0].substring(1,props.data[0].length)}: `">
        </Strong>
        <Span :text="`${props.data[1]}`">
        </Span>
    </li>
</template>

<style>
    :root {
        --dotSize: 4px;
        --dotLeft: -32px;
    }
    
    .prepTimeLi {
        position: relative;
        list-style-type: none;

        transform: translateY(-3px);
        margin-bottom: 8px;
    }

    .prepTimeLi::before {
        content: '';
        position: absolute;
        left: -32px;
        top: 50%;
        transform: translateY(-50%);
        width: var(--dotSize);
        height: var(--dotSize);
        background-color: var(--colorDarkCharcoal);
        border-radius: 50%;
    }
</style>
