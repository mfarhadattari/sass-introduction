# SASS - Syntactically Awesome Stylesheet

Sass is an extension to CSS and it is a CSS pre-processor. Sass reduces repetition of CSS.

## SASS Variables

### Variables are a way to store information that you can re-use later.

```scss
$variablename: value;
```

```scss
$myColor: red;
$myFontSize: 18px;
```

## Sass Nesting Styles

```scss
parentSelector {
  // css style here
  childSelector {
    // css style here
    grandChildSelector {
      // css style here
    }
  }
}
```

```scss
div {
  border: 2px solid black;
  width: 400px;
  margin: 20px auto;
  padding: 20px;
  h1 {
    text-align: center;
    font-size: 20px;
  }
  ul {
    border: 1px dashed red;
    li {
      color: green;
      p {
        font-size: 15px;
      }
    }
  }
}
```

## Sass Nesting Properties

```scss
properties: {
  sub-properties: value;
}
```

```scss
font: {
  family: Helvetica, sans-serif;
  size: 18px;
  weight: bold;
}

text: {
  align: center;
  transform: lowercase;
  overflow: hidden;
}
```

## Sass Import

```scss
@import fileName;
```

## Sass Partials

file name start with underscore like "\_colors.scss" which not auto transpile to css

## Sass @mixin and @include

### The @mixin directive create reused CSS code and the @include directive is use to include the mixin.

### @mixin

```scss
@mixin name($variable) {
  property: $variable;
  property: value;
  property: value;
}
```

```scss
@mixin important-text($color) {
  color: $color;
  font-size: 25px;
  font-weight: bold;
  border: 1px solid red;
  border-radius: 8px;
}
```

### @include

```scss
selector {
  @include mixin-name($variable);
}
```

```scss
.important-title {
  @include important-text(white);
  background-color: green;
  padding: 10px;
}
```

## Sass @extend

### The @extend directive lets you share a set of CSS properties from one selector to another.

```scss
@extend styleSelector;
```

## Sass Condition

- @if
- @else if
- @else

```css
@mixin conditionalText($val) {
  @if $val == danger {
    color: red;
  } @else if $val == alert {
    color: yellow;
  } @else if $val == success {
    color: green;
  } @else {
    color: black;
  }
}

.text-condition {
  @include conditionalText(danger);
}
```

## Sass for loop

```scss
@for $loopVariable from startValue through endValue {
  // style
}
```

```scss
@for $i from 1 through 5 {
  .col-#{$i} {
    width: 100%/5 * $i;
  }
}
```

## Sass While loop

```scss
$loopVariable: 1;
@while condition_of_loopVariable {
  // style
  // update loop variable
}
```

```scss
$j: 1;
@while $j <= 6 {
  .fs-#{$j} {
    font-size: 16px * $j;
  }
  $j: $j + 1;
}
```

## Sass each

```scss
@each item in array {
  //   style
}
```

```scss
@each $name, $color in $colors {
  .text-#{$name} {
    color: $color;
  }
}
```
