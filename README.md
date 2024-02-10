# Frontend Mentor - Blog preview card solution

This is a solution to the [Blog preview card challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/blog-preview-card-ckPaj01IcS). Frontend Mentor challenges help you improve your coding skills by building realistic projects. 

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
  - [Useful resources](#useful-resources)
- [Author](#author)
- [Acknowledgments](#acknowledgments)

**Note: Delete this note and update the table of contents based on what sections you keep.**

## Overview

### The challenge

Users should be able to:

- See hover and focus states for all interactive elements on the page

### Screenshot

![](./screenshot.jpg)

### Links

- Solution URL: [Github repo](https://github.com/theYuun/fem_recipe-page)
- Live Site URL: [Live site](https://theyuun.github.io/fem_recipe-page/)

## My process

### Built with

- Semantic HTML5 markup
- Grid
- Mobile-first workflow
- [Vue.js](https://vuejs.org) - The Progressive JavaScript Framework
- [Vite](https://vitejs.dev/) - Next Generation Frontent Tooling
- [npm](npmjs.com) - The world's largest software registry
- [Atomic Design](https://bradfrost.com/blog/post/atomic-web-design/) - "I wrote a book called Atomic Design, which covers all that goes into creating and maintaining effective design systems."

### What I learned

What a finnicky bloody project. I'm of the opinion that the person who created the reference images had a vendetta having made minor adjustments between the mobile and desktop versions.
The alignment was ever so slightly off between the two versions such that I had to add media queries at rather deep levels to ensure proper alignment.

All of that said, this is a grossly over-engineerd project. I used the Atomic Design Methodology to structure the project and although it is a very cool way to structure pretty much any project, especially with frameworks like Vue, it is a bit of a hassle moving between all the different files to try and find where the styles conflict. Do take a swing at the Atomic Design Methodology, it does give you a lot of breathing room when trying to manage a project.

I learned about the ```<slot></slot>``` element native to Vue 3, which is a very handy element. It probably does not cover all the bases that ```defineProps({})``` does, probably does some other things better too. It certainly helped with the Nutrition section. I wanted to start that with a ```<table></table>``` element and quickly ran into trouble in trying to add the lines between the rows. (Example 1)

Psuedo elements, you beautiful bastards! Did you know that you can't style ```::marker``` positions? This was particularly useless in the Ingredients section, where the crafty designer decided to have the bullets on the list vertically centered to the content.
I only remembered that ```::marker``` was an option when I looked at a fellow completer of this challenge, but did not notice the misalignment of the bullets on the Ingredient list.
In rides the ```::before``` element. Love this one and it's partner ```::after``` element! The customization on these bad boys can be manipulated using JavaScript even, with the help of CSS custom variables. I set about doing just that and unfortunately had to abandon this approach, given that Vue 3 appears not to handle psuedo class manipulation through custom variable setting all that well it seems. Or maybe I was missing something. In any case, targeting a psuedo class directly is not an option, as there's something about psuedo elements not being part of the DOM.
I tried 2 approaches from here, one where you can set a ```:style="{ '--x': props.x }"``` property directly in a HTML element (Example 2.1), the other where you need to target CSS variables that you create in your ```:root``` class and have Javascript manipulate these variables (Example 2.2). This was tricky, to be sure and it worked to a degree. I managed to set the ```content: ''``` property to a ```defineProps({})``` value, but getting it to respond properly ultimately did not work, as in Vue 3's lifecycle neither the ```onMounted()``` or ```watchEffect()``` functions did the trick, as phind suggested. I'll conquer these yet.
I ended up getting frustrated and lazy with my Atomic Design approach at this point and used the ```<slot></slot>``` elements to populate my lists with standard HTML ```<span></span>``` elements and I am not proud. [Example 2.3]

#### html
##### Example 1
```
// Child component
<template>
    <div class="appDiv"><slot></slot></div>
</template>

// Parent component
<template>
    // This here is the child's div
    <AppBlock class="app">
        // And this is what gets placed in the <slot></slot> element
        <RecipePage class="recipePage" :recipe="props.recipes[0]" />
    </AppBlock>
</template>
```
##### Examples 2.1 and 2.2
```
// Parent component to parent component
<CustomList :isOrdered="true" :data="props.data" />
// Parent Component
<CustomListUnordered v-if="!props.isOrdered" >
  <CustomListIndex :v-for="item in props.data" :data="props.data" />
</CustomListUnordered>
<CustomListOrdered v-if="props.isOrdered">
  <CustomListIndex :v-for="(item, index) in props.data" :bulletValue="index" :data="props.data" />
</CustomListOrdered>
```
##### Example 2.1
```
<li :style="{ '--x': props.x }" >{{ props.content }}</li>
```

#### css
##### Example 2.1
```
.listIndex {
  --bulletValue = '';
}
.listIndex::before {
  content: var(--bulletValue);
  /* ... */
}
```
##### Example 2.2
```
:root {
  --bulletValue: '';
}
.listIndex::before {
  content: var(--bulletValue);
  /* ... */
}
```
#### js
##### Example 2.2
```
const props = defineProps({
  bulletValue: {
    type: String,
  }
})
onMounted(() => {
  // or watchEffect(() => {
  // and yes, I know they do different things, but for this either can be used.
  document.querySelector(':root').style.setProperty('--bulletValue', props.bulletValue);
})
```

### Continued development

I have still to properly figure out the nuances of styling psuedo elements using Vue 3. Although I spent a lot of time, especially on the day I was set to commit this project, I was greatly hindered by the psuedo elements refusing, without errors, to render.

### Useful resources

- [phind](https://www.phind.com/search?home=true) - phind is very useful when trying to understand not just the part you're working on but you can also, if you phrase your question well enough and add your code to the prompt, get a verbose description of surrounding information as well.
- [Vue 3 + Vite](https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup)
- [VS Code](https://code.visualstudio.com/) + [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) (and disable Vetur) + [TypeScript Vue Plugin (Volar)](https://marketplace.visualstudio.com/items?itemName=Vue.vscode-typescript-vue-plugin).

## Author

- Frontend Mentor - [@theYuun](https://www.frontendmentor.io/profile/theYuun)
- freecodecamp - [theYuun](https://www.freecodecamp.org/theYuun)

## Acknowledgments

- The devs of phind
- The creator? of Atomic Design [Brad Frost](https://shop.bradfrost.com/)
- Some of the authors referenced in the phind results are as follows:
    - Regarding ```v-for="(item, index, key) in list"```[acdcjunior](https://stackoverflow.com/users/1850609/acdcjunior)
    - Regarding ```<slot></slot>``` elements [Solomon Eseme](https://enterprisevue.dev/blog/slots-in-vue-deep-dive/)