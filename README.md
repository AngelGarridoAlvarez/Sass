# Sass
CSS extension language

## .SCSS SYNTAX

Hace todo lo que hace css.

```scss
@mixin button-base() {
    @include typography(button);

display: inline-flex;
position: relative;
height: $button-height;
border: none;
vertical-align: middle;

&hover { cursor: pointer;}
}
```

## .SASS - INDENTED SYNTAX
Hace todo lo que hace css pero usando identations(sangrías) en lugar de usar semicolons (;) y curly braces ({})


```sass
@mixin button-base()
    @include typography(button)

    display: inline-flex
    position: relative
    height: $button-height
    border: none
    vertical-align: middle

    &hover
        cursor: pointer
```

## CSS VARIABLES VS SASS VARIABLES
Variables en css:
```css
:root{
    --primary-color: #272727;
    --accent-color: #ff652f;
    --text-color: #fff;
}

body {
    background: var(--primary-color);
}
```

Variables en sass:
```scss

```