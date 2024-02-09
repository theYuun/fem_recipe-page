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
    margin-top: 5px;
    margin-bottom: 0px;
    background-color: var(--colorWengeBrown);
}
</style>
