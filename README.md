# Frontend Mentor - Skilled e-learning landing page solution

This is a solution to the [Skilled e-learning landing page challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/skilled-elearning-landing-page-S1ObDrZ8q). Frontend Mentor challenges help you improve your coding skills by building realistic projects.

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Useful resources](#useful-resources)
- [Author](#author)

## Overview

### The challenge

Users should be able to:

- View the optimal layout depending on their device's screen size
- See hover states for interactive elements

### Screenshot

![](![alt text](image.png))

### Links

- Solution URL: (https://github.com/korcakSEA/skilled-elearning-landing-page.git)
- Live Site URL: (https://your-live-site-url.com)

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox, CSS Grid
- SASS
- Mobile-first workflow

### What I learned

In this project I learned different positioning techniques. Besides creating functions, and mixin in SASS.

You may see code snippets for buttons below:


```css
@mixin button($bg-color, $text-color, $hover-bg, $border: none, ) {
  // Basic button styles
  @include t.text-preset-7;
  background-image: $bg-color;
  color: $text-color;
  border: $border;
  padding: m.spacing(1.5) m.spacing(3);

  @include m.respond-to(tablet) {
    padding: m.spacing(2) m.spacing(4);
  }

  border-radius: m.px-to-rem(28);
  cursor: pointer;

  /* To position pseudo element */
  position: relative;
  /* To position correctly we will use flex layout */
  display: flex;
  justify-content: center;
  align-items: center;

  /* As transition does not work on background property with linear-gradient values, we will create pseudo element */
  /* Pseudo element is always relatively oriented button element */
  &::after {
    content: '';
    position: absolute;
    width: 100%;
    height: 100%;
    // Must be same as we will hide pseudo element behind the button
    border-radius: m.px-to-rem(28);
    opacity: 0;
    /* to display linear-gradient we use background-image property */
    background-image: $hover-bg;
    /* To place it behind the button */
    z-index: -1;
    // for opacity transition, so we can have smooth transition effect
    transition: opacity 0.3s ease-in;
  }

  &:hover::after,
  &:focus::after {
    opacity: 1;
  }
  &:hover {
    z-index: 0;
  }

}
```
### Useful resources

- (https://www.youtube.com/watch?v=PTVXnOrQoBQ) - This helped me learn how to create a button with a hover effect using linear-gradient. 
- (https://www.youtube.com/watch?v=nl9VlTA-AfE&t=8213s) - This helped me learn how to position  hero image with absolute positioning. 

## Author

- Frontend Mentor - [@korcakSEA](https://www.frontendmentor.io/profile/korcakSEA)

