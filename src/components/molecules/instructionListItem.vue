<script setup>
import { ref, defineProps } from 'vue';
import atoms from '../atoms/atoms';

const props = defineProps({
    data: {
        type: Array,
        required: true,
    },
    isOrderedValue: {
        type: Number,
        required: false,
    },
    index: {
        type: String,
        required: true,
    }
})

const ContentSpan = atoms.span;
const Strong = atoms.strong;

const item = ref([]);
Object.entries(props.data).forEach(([key, value]) => {
    item.value.push([key, value]);
});

</script>

<template>
    <li class="instructionListIndex" :aria-posinset="props.index">
        <span aria-hidden="true"><Strong :text="`${isOrderedValue + 1}.`"></Strong></span>
        <ContentSpan>
            <Strong :text="`${item[0][1]}: `"></Strong>{{`${item[1][1]}` }}
        </ContentSpan>
    </li>
</template>

<style scoped>
    .instructionListIndex {
        position: relative;
        list-style-type: none;
        margin-bottom: 8px;
        line-height: 23px;
    }

    .instructionListIndex span {
        position: absolute;
        left: -32px;
    }
</style>
