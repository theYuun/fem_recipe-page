<script setup>
import { ref, defineProps } from 'vue';

const props = defineProps({
    data: {
        type: Array,
        required: false,
    }
})


</script>

<template>
    <div class="nutritionDataDivider">
        <ul>
            <li v-for="(item, index) in props.data">
                <ul class="content">
                    <li class="description">{{ item[0] }}</li>
                    <li class="value">{{ item[1] }}</li>
                    <li class="line" v-if="index < props.data.length-1"><hr></li>
                </ul>
            </li>
        </ul>
    </div>
</template>

<style scoped>
    div, ul, li {
        margin: 0;
        padding: 0;
        list-style-type: none;
    }
    .nutritionDataDivider {
        margin-top: 25px;
    }
    hr {
        margin: 13px;
    }
    .content {
        margin: 0;
        padding: 0;
        display: grid;
        grid-template-columns: 50% 50%;
        grid-template-areas:
        'description value'
        'line line';
        color: var(--colorDarkCharcoal);
    }
    .description {
        margin: 0;
        padding-left: 32px;
        grid-area: description;
    }
    .value {
        margin: 0;
        padding-left: 8px;
        grid-area: value;
        font-weight: 800;
    }
    .line {
        margin: 0;
        grid-area: line;
    }

    @media (min-width: 376px) {
        
        .value {
            padding-left: 13px;
        }
    }
</style>
