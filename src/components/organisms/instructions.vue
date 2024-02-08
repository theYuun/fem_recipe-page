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

const Block = molecules.instructionDiv;
const Heading2 = atoms.Heading2;
const List = molecules.instructionList;

</script>

<template>
    <Block>
        <Heading2 :text="'Instructions'"/>
        <List :isOrdered="true" :items="[...props.data]" />
    </Block>
</template>

<style scoped>
</style>
