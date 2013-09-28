# ice.scss

A collection of SCSS patterns (placeholders and mixins).

Although Ice borrows many concepts and code from several other projects, including Bootstrap, Foundation, and Bourbon, it has a different philosophy:

* **Minimal** - Ice does not generate any CSS unless you tell it to.

* **Just a toolbox** - Ice provides *patterns*. How and if you use them is up to you. You only get what you use.

* **Bring your own style guide** - Ice does not dictate how your CSS should be organized and how you name your selectors.

* **Performant** - Ice tries to group selectors and minimize CSS overrides leading to smaller file size and faster rendering times.

### Example

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

* Testing
* Documentation
* Remove dependencies (bourbon, normalize), include some code from those in ice/addons, ice/css3, ice/grid and ice/normalice.
* Themable
* Resources

## Resources & Further Reading

* Responsive
    * http://thesassway.com/intermediate/responsive-web-design-in-sass-using-media-queries-in-sass-32 
* Typography
    * http://filamentgroup.com/lab/how_we_learned_to_leave_body_font_size_alone/   
