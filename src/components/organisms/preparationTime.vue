<script setup>
import { ref, defineProps } from 'vue';
import atoms from '../atoms/atoms';
import molecules from '../molecules/molecules';

const Heading3 = atoms.Heading3;
const PrepList = molecules.preparationList;
const PrepBlock = molecules.preparationDiv;

const props = defineProps({
    data: {
        type: Object,
        required: true,
    }
})
</script>

<template>
    <PrepBlock>
        <Heading3 :text="`Preparation time`" />
        <PrepList :items="props.data" />
    </PrepBlock>
</template>

<style>
</style>
