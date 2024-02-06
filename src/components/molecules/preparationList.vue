<script setup>
import { ref, defineProps } from 'vue';
import molecules from './molecules.js';

const ListItem = molecules.preparationTimeListItem;

const props = defineProps({
    isOrdered: {
        type: Boolean,
        required: false,
    },
    items: {
        type: Object,
        required: true,
    }
})

const items = ref([])
Object.entries(props.items).forEach(([key, value]) => {
    items.value.push([key, value]);
});

</script>

<template>
    <ul v-show="!props.isOrdered">
        <ListItem v-for="item in items" :data="item" />
    </ul>
    <ol v-show="props.isOrdered">
        <ListItem v-for="item in items" :data="item" />
    </ol>
</template>

<style scoped>
</style>
