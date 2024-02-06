<script setup>
import { ref, defineProps } from 'vue';
import atoms from './atoms';

const props = defineProps({
    data: {
        type: Array,
        required: true,
    }
})

const TableCell = atoms.tableCell;

</script>

<template>
    <tr>
        <TableCell v-for="item in props.data" :data="item" />
    </tr>
</template>

<style scoped>
</style>
