<script setup>
import { ref, defineProps } from 'vue';
import atoms from '../atoms/atoms'
import molecules from '../molecules/molecules';

const props = defineProps({
    data: {
        type: Array,
        required: true,
    }
})

const Heading2 = atoms.Heading2;
const List = molecules.ingredientList;

</script>

<template>
    <Heading2 :text="'Instructions'"/>
    <List :items="[...props.data]" />
</template>

<style scoped>
</style>
