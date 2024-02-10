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
    },
})

const ListItem = atoms.ListItem;

</script>

<template>
    <ul v-if="!props.isOrdered">
        <ListItem v-for="item in props.items" >
            <span class="content"  :aria-label="`${item}`">{{ item }}</span>
        </ListItem>
    </ul>
    <ol v-if="props.isOrdered">
        <ListItem v-for="item in props.items" >
            <span class="content" :aria-label="`${item}`">{{ item }}</span>
        </ListItem>
    </ol>
</template>

<style scoped>
    ul, ol {
        margin-left: 24px;
        margin-top: 20px;
    }
</style>
