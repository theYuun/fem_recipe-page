<script setup>
import { ref, defineProps } from 'vue';
import molecules from './molecules.js';

const ListItem = molecules.ingredientListItem;

const props = defineProps({
    items: {
        type: Array,
        required: true,
    }
})

</script>

<template>
    <div class="ingredientList" >
        <ListItem v-for="(item, index) in props.items" :data="item" :index="index" />
    </div>
</template>

<style scoped>
    .ingredientList {
        margin-top: 19px;
    }
</style>
