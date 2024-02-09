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

- Solution URL: [Github repo](https://github.com/theYuun/fem_blog-preview-card)
- Live Site URL: [Live site](https://theyuun.github.io/fem_blog-preview-card/)

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- Mobile-first workflow
- [Vue.js](https://vuejs.org) - The Progressive JavaScript Framework
- [Vite](https://vitejs.dev/) - Next Generation Frontent Tooling
- [npm](npmjs.com) - The world's largest software registry
- [INKSCAPE](https://inkscape.org/) - Draw Freely

### What I learned

What a cool project to do using Vue.js. I had a lot of fun doing it.
That said, what an ache in the backside to get images loading on Github Pages. I went through so many solutions that phind suggested and it seems that a slight difference to the original code was what was needed.

Setting up the link to ensure Vue can get the proper location for the images was quite a thing.
To think, I built a way more complex project previously that called data in from a fake server and it lined up perfectly. The project was for a job interview that I unfortunately did not get, mainly due to some missing expectations (testing components). Images are a beast of their own and to a degree I'm not sure why it's working now. I'm just relieved that it's working.
Firstly, I had to move the files into the public folder and ensure that the reference to those files are working.
Some of the solutions included adding a ```new URL()``` function that houses the reference which the Vite building process converts to the required reference for Github Pages can then further convert to a working link. (Example 1)
> Sometimes it just seems that there are too many steps between the dev and the running website, but then I know too little to really comment on that.

I added an additional data object to check the effectivity of the dynamic nature of what I was building, putting Vue's componentized functionality to use.
One does not simply try and make the data linkages, you aught to go through the different functions and decide whether the ```computed()``` or ```ref()``` function should be used. Thankfully phind was there to illuminate the difference.
One does not simply ```<style scoped>``` and assume everything's going to work out fine. Rather create class names on elements and target those ```.objectListItem {}```, than a ```.object li {}```. Ensure you know what you're targeting, lest the style spill over to other elements that you did not mean to target. Not to say that more complicated selectors should never be utilized, like ```.object li:has() {}```, but be careful that future-you and others can read the stylesheet and easily get what's going on. I had some odd floxbox behaviour spilling over when I went the ```<style scoped>``` route. (Example 2)
> I was against the complicatedness of componentized frameworks like Vue when I first tried to learn Angular, but building a Vanilla Javascript componentized app as practice made me understand and appreciate it so much more.

I'm not entirely sure whether this is the best way to tackle a new project, but ensure you have the HTML skeleton first, the JavaScript musculature second, the serving ecosystem third so you can focus your future frustrations out on the CSS fourth. This seems safe.
> Too many times I'd see style issues in among the other steps to find that I'd lost track of what I was doing before tackling those style issues.

I've gotten more used to the aria attributes having installed a screen reader extention.
I played around with this a bit and set them up to be data-driven. (Example 3)
> Install one and have a listen to how I labelled the elements in this app.
> A note that Screen Readers do not practice quolloque all that well. Vue.js is pronounced as 'Voo dot jay es'


####html
(Example 3)
```
  <h1 class="name" :aria-label="`The article name is ${blogDetails.name}`">{{ blogDetails.name }}</h1>
```
####css
####js
(Example 1)
```
  const authorImageName = props.blogDetails.author.replace(' ', '');
  const articleID = props.blogDetails.id.toString();
  const blogHeaderImagePath = computed( () => {
      return `/fem_blog-preview-card/images/${authorImageName}/articles/${articleID}/image-header.svg`;
      // The below did not work and also required messing around in the vite.config.js file, which I'm not comfortable doing just yet
      // return new URL(`/fem_blog-preview-card/public/images/${authorImageName}/articles/${articleID}/image-header.svg`, import.meta.url).href;
  })
  const blogAuthorImagePath = computed(() => {
      return `/fem_blog-preview-card/images/${authorImageName}/image-author.webp`;
      //return new URL(`/fem_blog-preview-card/public/images/${authorImageName}/image-author.webp`, import.meta.url).href;
  })
```

### Continued development

I'll definitely be referencing this project in the future when I need to load images from data.

### Useful resources

- [phind](https://www.phind.com/search?home=true) - phind is very useful when trying to understand not just the part you're working on but you can also, if you phrase your question well enough and add your code to the prompt, get a verbose description of surrounding information as well.

## Author

- Frontend Mentor - [@theYuun](https://www.frontendmentor.io/profile/theYuun)
- freecodecamp - [theYuun](https://www.freecodecamp.org/theYuun)

## Acknowledgments

- The devs of phind
- The creator? of Atomic Design [Brad Frost](https://shop.bradfrost.com/)
- Some of the authors referenced in the phind results are as follows:
    - Regarding ```v-for="(item, index, key) in list"```[acdcjunior](https://stackoverflow.com/users/1850609/acdcjunior)
    - Regarding ```<slot></slot>``` elements [Solomon Eseme](https://enterprisevue.dev/blog/slots-in-vue-deep-dive/)
    - []()
    - []()
    - []()
    - []()
    - []()
    - []()
    - []()



# Vue 3 + Vite

This template should help get you started developing with Vue 3 in Vite. The template uses Vue 3 `<script setup>` SFCs, check out the [script setup docs](https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup) to learn more.

## Recommended IDE Setup

- [VS Code](https://code.visualstudio.com/) + [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) (and disable Vetur) + [TypeScript Vue Plugin (Volar)](https://marketplace.visualstudio.com/items?itemName=Vue.vscode-typescript-vue-plugin).
