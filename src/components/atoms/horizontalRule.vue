<script setup>
import { ref, defineProps } from 'vue';
const props = defineProps({
    identifier: {
        type: String,
        required: false,
    },
    customStyle: {
        type: Object,
        required: false,
    }
})
</script>

<template>
    <hr id="hr">
</template>

<style scoped>
#hr {
    margin: 30px 0;
    background-color: var(--colorWengeBrown);
}
</style>
