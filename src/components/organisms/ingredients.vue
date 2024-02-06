<script setup>
import { ref, defineProps } from 'vue';
import atoms from '../atoms/atoms'

const props = defineProps({
    data: {
        type: Array,
        required: true,
    }
})

const Heading2 = atoms.Heading2;
const List = atoms.List;

</script>

<template>
    <Heading2 :text="'Ingredients'"/>
    <List :items="[...props.data]" />
</template>

<style scoped>
</style>
