# Primer

Primer is pure Sass.
Human-readable: We aim for clarity over brevity.
Simple

## Features

* Base 8 Grid(Soft)
* BEM Selector Naming
* SMCSS declaration sorting (post processor)
* Mobile First

## Mixin Library

### BEM

#### Block Element Modifier

[http://getbem.com/naming/](http://getbem.com/naming/)

Modifier names may consist of Latin letters, digits, dashes and 
underscores. CSS class is formed as block’s or element’s name plus 
two dashes: .block--mod or .block__elem--mod and .block--color-black 
with .block--color-red. Spaces in complicated modifiers are replaced by dash.

```css
.form { }
.form--theme-xmas { }
.form--simple { }
.form__input { }
.form__submit { }
.form__submit--disabled { }
```

#### Scalable and Modular Architecture for CSS

Declaration Sorting
[http://smacss.com/book/categorizing](http://smacss.com/book/categorizing)

1. Base
2. Layout
3. Module
4. State
5. Theme

#### Gulp
[https://www.npmjs.com/package/css-declaration-sorter](https://www.npmjs.com/package/css-declaration-sorter)
If you use gulp I would recomend using 'CSS Declaration Sorter' that will organize your CSS for production.

### Grid
Softgrid, base 8px

[https://builttoadapt.io/intro-to-the-8-point-grid-system-d2573cde8632](https://builttoadapt.io/intro-to-the-8-point-grid-system-d2573cde8632)

#### Pixels for layout
#### Flex
#### CSS Grid

### Containerize
A container is an element with a max-width and equal left / right margins. This can be used to set the primary column and page gutters. Containers can be used to organize rows.


```html
<div class="container">
  <div class="row"></div>
  <div class="row"></div>
</div>
```

### Media
Mobile First Media Queries

```css
  @include media($md-breakpoint) {
    width: 100%;
    height: 100vh;
    max-height: 850px;
  }    

  CSS OUTPUT

```

### Buttonize
Setting proper accessibility and states

```scss
  :hover
  :focus
  :active
  :disabled
  :disabled:active
  .is-disabled,
  .is-disabled:active
```

### Iconize
Helper


```scss
Options Before/After
```

### Prefix
Mixin to Add Vendor Prefixes 

### Prefix-keyframes
Special case to add Vendor Prefixes for keyframes

### EM
Utility Mixin to Convert pixels to EMs, use this for media queries and thats about

#### Suggested Use: Media Queries

### REM
Utility Mixin to Convert pixels to REMs, use this for font sizing

#### Suggested Use: Font-Sizing