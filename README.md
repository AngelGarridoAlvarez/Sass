# Sass
CSS extension language

## .SCSS SYNTAX

Hace todo lo que hace css pero de forma más sencialla.

Los navegadoes no leen scss, hay que usar un compilador.

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
// CSS variable
$primary-color: #272727;
$accent-color: #ff652f;
$text-color: #fff;

$mobile: 800px;

```

## MAPS
Similares a los arrays
```scss
// Podemos definir una variable usando maps
$font-weights: (
    "regular": 400,
    "medium": 500,
    "bold": 700
);

body {
    font-weight: map-get($font-weights, bold);
    }
```


## IMPORTS - PARTIALS
Creo el archivo _restes-scss y _variables.scss y luego solo tengo que poner en el archivo scss que vaya a utilizar:
```scss
@import './resets';
@import './variables';
```




## NEST
```scss
.main {
    @include flexcenter(row);
    // Calculations: you can use it without calc()
    width: 80%-10%;
    margin: 0 auto;

    // Instead of ".main__paragraph" we can use &__paragraph
    // & equals the parent
    &__paragraph {
        font-weight: weight(regular);
        color: blue;
        &:hover {
            color: pink;
        }
    }


    @include mobile{
        flex-direction: column;
    }
}
```


## FUNCTIONS
```scss
@function weight($weight-name) {
    @return map-get($font-weights, $weight-name);
}
```


## MIXIN

Mixin: similar to fucntions, but it should be used for styles, instead functions should be used to compute values and return values.

```scss
@mixin flexcenter($direction) {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: $direction;
}
```


## EXTEND
```scss
.main {
    @include flexcenter(row);
    // Calculations: you can use it without calc()
    width: 80%-10%;
    margin: 0 auto;

    // Instead of ".main__paragraph" we can use &__paragraph
    // & equals the parent
    &__paragraph {
        font-weight: weight(regular);
        color: blue;
        &:hover {
            color: pink;
        }
    }

    &__paragraph2 {
        @extend .main__paragraph;

        &:hover{
            color: $accent-color;
        }
    }
}
```