# Primer (alpha)

Primer is simple mixin library for builing out larger more complex design systems.

## Methodology

- Mobile First
- BEM: Selector Naming
- SMCSS: Declaration Sorting
- Soft Grid
- Human-readable

## Mixins

- bem
- buttonzine
- containerize
- em
- grid
- iconize
- media
- prefix-keyframes
- prefix
- rem

### Selector Naming: BEM

Block Element Modifier
[http://getbem.com/naming/](http://getbem.com/naming/)

Modifier names may consist of Latin letters, digits, dashes and
underscores. CSS class is formed as block’s or element’s name plus
two dashes: .block--mod or .block\_\_elem--mod and .block--color-black
with .block--color-red. Spaces in complicated modifiers are replaced by dash.

```scss
.button {
  @include elem('primary') {
    background-color: blue;
  }
  @include mod('is-disabled') {
    opacity: 0.5;
  }
}

.button {
  .button__primary {
    background-color: blue;
  }

  .button--is-disabled {
    opacity: 0.5;
  }
}
```

Human readable standard. How it is spoken.

menu\_\_primary

menu\_\_secondary

prefered -> primary-menu\_\_

#### Declaration Sorting: SMACSS

Scalable and Modular Architecture for CSS
[http://smacss.com/book/categorizing](http://smacss.com/book/categorizing)

1. Base
2. Layout
3. Module
4. State
5. Theme

#### \*Gulp Tip

If you use gulp I would recomend using 'CSS Declaration Sorter' that will organize your CSS for production. You can choose the smacss settings to enforce that standard. You will get a performance benifit of smaller file size by doing this.

[https://www.npmjs.com/package/css-declaration-sorter](https://www.npmjs.com/package/css-declaration-sorter)

#### Prettier for formating

Standardizing code formating is important when working with other developers, prettier takes care of this automatically.
[https://prettier.io/docs/en/configuration.html](https://prettier.io/docs/en/configuration.html)

### Containerize

A container is an element with a max-width and equal left / right margins. This can be used to set the primary column and page gutters. Containers can be used to organize rows.

```scss
.container {
  @include containerize;
  padding: $gutter 0;
}
```

```html
<div class="container">
  <div class="row"></div>
  <div class="row"></div>
</div>
```

### Media

Mobile first media queries

```scss
@include media($md-breakpoint) {
  width: 100%;
  height: 100vh;
  max-height: 850px;
}

/* Output */
@media only screen and (min-width: 1100px) {
  width: 100%;
  height: 100vh;
  max-height: 850px;
}
```

### Buttonize

Button reset, sets desired accessibility options and states.

```scss
@include buttonize();
```

- `:hover`
- `:focus`
- `:active`
- `:disabled`
- `:disabled:active`
- `.is-disabled`
- `.is-disabled:active`

### Iconize

Icon reset, set desired options for displaying an font icon.

```scss
span {
  @include iconize($icon-family, $icon-uni, $side: 'before'): ;
}

span {
  speak: none;
  font-family: $icon-family;
  font-style: normal;
  font-weight: normal;
  font-variant: normal;
  text-transform: none;
  line-height: normal;

  /* Better Font Rendering =========== */
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;

  &:before {
    content: '$icon-uni';
  }
}
```

- `icon-family` Font-Family
- `icon-uni` Unicode Value
- `side` Before or after

### Prefix

Use this to add vendor prefixes.

```scss
a {
  @include prefix(transition, color 0.15s linear, webkit ms);
}

/* Output */
a {
  -webkit-transition: color 0.15s linear;
  -ms-transition: color 0.15s linear;
  /* Output standard non-prefixed declaration */
  transition: color 0.15s linear;
}
```

### Prefix-keyframes

Special case to add Vendor Prefixes for keyframes.

```scss
@mixin keyframes($name) {
  @-webkit-keyframes #{$name} {
    @content;
  }
  @keyframes #{$name} {
    @content;
  }
}
```

### Grid

Functiont to standardize spacing. Based on an 8px grid system. This means the smallest increment between items is 8px (or 4px) and all spaces are divisible by 8px(or 4). This insures spacing is optimized to pixel based displays and all spacing is proportional to each other. Spacing is relative to the adjacent element.

[https://builttoadapt.io/intro-to-the-8-point-grid-system-d2573cde8632](https://builttoadapt.io/intro-to-the-8-point-grid-system-d2573cde8632)

```css
margin-bottom: g(8);

/* Output */
margin-bottom: 64px;
```

#### Pixels for layout

The prefered units for element sizing, vertical and horizontal spacing is percents and pixels.

#### Suggested Use: Padding, Margin, Width, Height

### EM

Function to convert pixels to EMs, use this for Media Queries.

#### Suggested Use: Media Queries

```scss
em($pixels, $context: $base-font-size);

```

### REM

Function to convert pixels to REMs, use this for font sizing.

#### Suggested Use: Font-Sizing

```scss
rem($pixels, $root_context: $base-font-size);

```

### Flexbox

Use Flexbox to organize inline media.

### CSS Grid

Use CSS Grid to create layouts.

### Layers

Z-index management

### Animation

hardware acceleration
