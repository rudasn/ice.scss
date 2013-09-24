# ice.scss

A collection of SCSS patterns (placeholders and mixins).

**Ice does not produce any CSS unless you tell it to.**

Ice does not define any class names or any selectors. You are responsible for defining your own selectors according to your project's existing style guides.

Since Ice is based on SCSS placeholders and mixins, you get the added benefit of having **grouped selectors** instead of the same rules defined and applied in multiple places. This makes your CSS much smaller and compact.

## Example

Let's say you just need to define a simple, responsive two-column layout.

In your ```.scss``` file:

```scss
@import "ice/ice";

.my-layout {
    @extend %ice-block-container;

    .my-content {
        @include ice-respond($ice-respond-tablet-desktop) {
            float: left;
            width: 70%;
        }
    }
    .my-sidebar {
        @include ice-respond($ice-respond-tablet-desktop) {
            float: right;
            width: 30%;
        }
    }
}
```

Produces the following CSS:

```css
.my-layout:before, .my-layout:after {
  content: "";
  display: table;
}
.my-layout:after {
  clear: both;
}

.my-layout {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}

.my-layout {
  position: relative;
  margin-left: auto;
  margin-right: auto;
  max-width: 980px;
}

@media only screen and (min-width: 768px) {
  .my-layout .my-content {
    float: left;
    width: 70%;
  }
}
@media only screen and (min-width: 768px) {
  .my-layout .my-sidebar {
    float: right;
    width: 30%;
  }
}
```

## Features

### Blocks

### Typography

### Forms

### Navigation

### Responsive

### Helpers

## Roadmap
* Documentation

## Resources
* Responsive
    * http://thesassway.com/intermediate/responsive-web-design-in-sass-using-media-queries-in-sass-32 
* Typography
    * http://filamentgroup.com/lab/how_we_learned_to_leave_body_font_size_alone/   
