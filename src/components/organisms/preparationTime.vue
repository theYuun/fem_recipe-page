<script setup>
import { ref, defineProps } from 'vue';
import atoms from '../atoms/atoms';
import molecules from '../molecules/molecules';

const Heading3 = atoms.Heading3;
const List = molecules.preparationList;

const props = defineProps({
    data: {
        type: Object,
        required: true,
    }
})
</script>

<template>
    <Heading3 :text="`Preparation Time`" />
    <List :items="props.data" />
</template>

<style scoped>
</style>
