<script setup>
import { ref, defineProps } from 'vue';
const props = defineProps({
    data: {
        type: Array,
        required: true,
    }
})

const item = ref([])
Object.entries(props.data).forEach(([key, value]) => {
    item.value.push([key, value]);
});

</script>

<template>
    <li><strong>{{ `${item[0][1]}: `}}</strong>{{`${item[1][1]}` }}</li>
</template>

<style scoped>
</style>
