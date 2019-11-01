# Primer (alpha)

Primer is simple mixin library for builing out larger more complex design systems.

## Features

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
- media-queries
- prefix-keyframes
- prefix
- rem

### Block Element Modifier

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

```css
g(8)

```

#### Pixels for layout

The prefered units for element sizing is percents and pixels.

#### Flexbox

Use flexbox to organize inline media.

#### CSS Grid

Use CSS Grid to create layouts.

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

```scss
@include media($md-breakpoint) {
  width: 100%;
  height: 100vh;
  max-height: 850px;
}

@media only screen and (min-width: 1100px) {
  width: 100%;
  height: 100vh;
  max-height: 850px;
}
```

### Buttonize

Setting proper accessibility and states

```scss
@include buttonize(): ;
```

- `:hover`
- `:focus`
- `:active`
- `:disabled`
- `:disabled:active`
- `.is-disabled`
- `.is-disabled:active`

#### Theming

```scss
$button-padding-default: 9px 24px 10px 24px !default;
$button-padding-small: 4px 24px !default;
$button-background-color: linear-gradient(
  to bottom,
  $white,
  $subtle-gray
) !default;
$button-background-color--hover: linear-gradient(
  to bottom,
  $subtle-gray,
  $white
) !default;
$button-background-color--focus: linear-gradient(
  to bottom,
  $subtle-gray,
  $white
) !default;
// -webkit-linear-gradient(top, $subtle-gray, $white)
$button-background-color--active: $light-gray !default;
$button-border-color: $medium-gray !default;
```

### Iconize

```scss
@include iconize($icon-family, $icon-uni, $side: 'before'): ;
```

- `icon-family` Font-Family
- `icon-uni` Unicode Value
- `side` Before or after

### Prefix

Mixin to Add Vendor Prefixes

```scss
a {
  @include prefix(transition, color 0.15s linear, webkit ms);
}

a {
  -webkit-transition: color 0.15s linear;
  -ms-transition: color 0.15s linear;
  /* Output standard non-prefixed declaration */
  transition: color 0.15s linear;
}
```

### Prefix-keyframes

Special case to add Vendor Prefixes for keyframes

```scss
Example
```

### EM

Function to Convert pixels to EMs, use this for media queries and thats about

#### Suggested Use: Media Queries

```scss
em($pixels, $context: $base-font-size);

```

### REM

Function to convert pixels to REMs, use this for font sizing

#### Suggested Use: Font-Sizing

```scss
rem($pixels, $root_context: $base-font-size);

```
