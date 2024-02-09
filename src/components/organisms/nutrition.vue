<script setup>
import { ref, defineProps } from 'vue';
import atoms from '../atoms/atoms'
import molecules from '../molecules/molecules';

const props = defineProps({
    data: {
        type: Object,
        required: true,
    }
})

const Block = molecules.nutritionDiv;
const Heading2 = atoms.Heading2;
const Spacer = atoms.spacer;
const Paragraph = atoms.Paragraph;
const NutritionData = molecules.nutritionData;

// Copy the nutrition object's key/value pairs into an array
const items = ref([]);
Object.entries(props.data).forEach(([key, value]) => {
    items.value.push([key, value]);
});

// Remove the description entry of the nutrition object
items.value.shift();

// Capitalize the decriptions
items.value.forEach((subArray) => {
    subArray[0] = subArray[0].charAt(0).toUpperCase() + subArray[0].slice(1);
})

</script>

<template>
    <Block>
        <Heading2 :text="'Nutrition'"/>
        <Spacer :margins="'-6px 0 0 0'" />
        <Paragraph :text="props.data.description" />
        <NutritionData :data="items" />
    </Block>
</template>

<style scoped>
</style>
