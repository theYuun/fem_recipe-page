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
//const List = atoms.List;
const List = molecules.ingredientList;
const Block = molecules.ingredientDiv;

</script>

<template>
    <Block>
        <Heading2 :text="'Ingredients'"/>
        <List :items="[...props.data]" />
    </Block>
</template>

<style>

</style>
