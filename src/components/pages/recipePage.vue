<script setup>
import { ref, defineProps, computed } from 'vue';
import organisms from '../organisms/organisms';
import atoms from '../atoms/atoms.js';
import molecules from '../molecules/molecules';

const props = defineProps({
    recipe: {
        type: Object,
        required: true,
    },
})

const Image = atoms.Image;
const Heading1 = atoms.Heading1;
const Paragraph = atoms.Paragraph;
const PreparationTime = organisms.preparationTime
const Ingredients = organisms.ingredients;
const HorizontalRule = atoms.HorizontalRule;
const Instructions = organisms.instructions;
const Nutrition = organisms.nutrition;
const ContentBlock = molecules.contentDiv;
const RecipePageBlock = molecules.recipePageDiv;

const imageRef = computed(() => {
    return `/fem_recipe-page/images/image-${props.recipe.name.replaceAll(' ', '')}.jpeg`
})

</script>

<template>
    <RecipePageBlock class="recipePage">
        <Image :url="imageRef" />
        <ContentBlock>
            <Heading1 :text="props.recipe.name" />
            <Paragraph :text="props.recipe.description"/>
            <PreparationTime :data="props.recipe.preparation" />
            <Ingredients :data="props.recipe.ingredients" />
            <HorizontalRule />
            <Instructions :data="props.recipe.instructions" />
            <HorizontalRule />
            <Nutrition :data="props.recipe.nutrition" />
        </ContentBlock>
    </RecipePageBlock>
</template>

<style>
</style>
