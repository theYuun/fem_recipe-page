<script setup>
import { ref, defineProps } from 'vue';
import molecules from './molecules.js';

const ListItem = molecules.instructionListItem;

const props = defineProps({
    isOrdered: {
        type: Boolean,
        required: false,
    },
    items: {
        type: Array,
        required: true,
    }
})

</script>

<template>
    <ul v-show="!props.isOrdered">
        <ListItem v-for="item in props.items" :data="item" />
    </ul>
    <ol v-show="props.isOrdered">
        <ListItem v-for="item in props.items" :data="item" />
    </ol>
</template>

<style scoped>
</style>
