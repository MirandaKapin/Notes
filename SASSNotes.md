# Sass Notes

## Reusable mixins

### border-radius
``` sass
@mixin border-radius($radius) {
      -webkit-border-radius: $radius;
         -moz-border-radius: $radius;
              border-radius: $radius;
}
```

### Clearfix
``` sass
@mixin clearfix {
  &:after {
    content: "";
    display: table;
    clear: both;
  }
}
```
