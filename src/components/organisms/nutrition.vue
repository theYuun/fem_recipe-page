<script setup>
import { ref, defineProps } from 'vue';
import atoms from '../atoms/atoms'

const props = defineProps({
    data: {
        type: Object,
        required: true,
    }
})

const Heading2 = atoms.Heading2;
const Paragraph = atoms.Paragraph;
const Table = atoms.table;

// Copy the nutrition object's key/value pairs into an array
const items = ref([]);
Object.entries(props.data).forEach(([key, value]) => {
    console.log(key + ' : ' + value);
    items.value.push([key, value]);
});

// Remove the description entry of the nutrition object
items.value.shift();

</script>

<template>
    <Heading2 :text="'Nutrition'"/>
    <Paragraph :text="props.data.description" />
    <Table :data="items" />
</template>

<style scoped>
</style>
