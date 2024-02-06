<script setup>
import { ref, defineProps } from 'vue';
import atoms from './atoms.js';

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

const ListItem = atoms.ListItem;

</script>

<template>
    <ul v-show="!props.isOrdered">
        <ListItem v-for="item in props.items" :text="item" />
    </ul>
    <ol v-show="props.isOrdered">
        <ListItem v-for="item in props.items" :text="item" />
    </ol>
</template>

<style scoped>
</style>
