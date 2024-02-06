<script setup>
import { ref, defineProps } from 'vue';
import atoms from './atoms';

const props = defineProps({
    data: {
        type: Array,
        required: true,
    }
})

const TableRow = atoms.tableRow;

</script>

<template>
    <table>
        <TableRow v-for="item in props.data" :data="item" />
    </table>
</template>

<style scoped>
</style>
