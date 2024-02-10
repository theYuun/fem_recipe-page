<script setup>
import { ref, defineProps } from 'vue';
import molecules from './molecules.js';

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

const ListItem = molecules.instructionListItem;

</script>

<template>
    <ul v-show="!props.isOrdered">
        <ListItem v-for="(item, index) in props.items" :data="item" :index="index" />
    </ul>
    <ol v-show="props.isOrdered">
        <ListItem v-for="(item, index) in props.items" :data="item" :isOrderedValue="index" :index="index" />
    </ol>
</template>

<style scoped>
ul, ol {
    margin-top: 20px;
    margin-right: 0;
}
</style>
