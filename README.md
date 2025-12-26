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
  - [Useful resources](#useful-resources)
- [Author](#author)

## Overview

### The challenge

Users should be able to:

- See hover and focus states for all interactive elements on the page

### Screenshots

Mobile - 375px

![](./screenshots-solution/mobile-375px.png)

Desktop - 1440px

![](./screenshots-solution/desktop-1440px.png)

Hover over "HTML & CSS foundations"

![](./screenshots-solution/mobile-375px-hover.png)

### Links

- [Github Repo](https://github.com/Leondvin/blog-preview-card-solution)
- [Live Site URL - Github Pages](https://leondvin.github.io/blog-preview-card-solution/)

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties (variables)
- Flexbox
- Mobile-first workflow
- Media query - @media
- Feature query - @supports
- Vendor prefixes - -webkit-, -moz-

### What I learned

I used `width: fit-content;` to set the width of a block-level element, `.status`, to wrap up within its content.

I added fallback rules for old browsers by putting the rules with the **vendor prefixes**, `-webkit-` and `-moz-` before the modern declaration, `width: fit-content;`.

The addition of `display: inline-block;` as the fallback for IE, since none of the versions of IE employs any of the mentioned **vendor prefixes**.

```css
.status {
  /* CSS rules */
  display: inline-block;  /* fallback for IE */
  width: -webkit-fit-content;
  width: -moz-fit-content;
  width: fit-content;
}
```

Since some old browsers [don't support](https://caniuse.com/?search=dvh) `dvh` (dynamic viewport height) `vh` (viewport height) is added as the fallback unit.

Instead of putting the modern version of the rule after the fallback inside the same ruleset, the `@supports` at-rule is used to apply the modern rule if the browser supports `dvh`.

```css
main {
  /* CSS rules */
  min-height: 100vh;
}
@supports (min-height: 100dvh) {
  main {
      min-height: 100dvh;
  }
}
```

### Useful resources

- [MDN - fit-content](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Values/fit-content)
- [MDN - Vendor prefix](https://developer.mozilla.org/en-US/docs/Glossary/Vendor_Prefix)
- [MDN - Using feature queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Conditional_rules/Using_feature_queries)
- [DEV - CSS *vh (dvh, lvh, svh) and *vw units](https://dev.to/frehner/css-vh-dvh-lvh-svh-and-vw-units-27k4)

## Author

- Github - [@Leondvin](https://github.com/Leondvin)
- Frontend Mentor - [@Leondvin](https://www.frontendmentor.io/profile/Leondvin)
