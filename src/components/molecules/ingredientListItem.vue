<script setup>
import { ref, defineProps, onMounted } from 'vue';
import atoms from '../atoms/atoms';

const props = defineProps({
    data: {
        type: Array,
        required: true,
    },
    isOrderedValue: {
        type: String,
        required: false,
    }
})
const isOrdered = false;
onMounted(() => {
    if(props.isOrderedValue)
        isOrdered = true;
})

</script>

<template>
    <li class="ingredientListIndex">
        <div class="unorderedBullet" v-if="!isOrdered" ></div>
        <span class="unorderedSpan" v-if="!isOrdered">{{ props.data }}</span>
    </li>
</template>

<style scoped>
    .ingredientListIndex {
        position: relative;
        list-style-type: none;
        margin-bottom: 8px;
        margin-left: 40px;
        line-height: 23px;
    }

    .unorderedBullet {
        content: '';
        position: absolute;
        top: 50%;
        left: -31px;
        transform: translateY(-50%);
        width: 3px;
        height: 3px;
        border-radius: 50%;
        background-color: var(--colorWengeBrown);
    }
</style>
