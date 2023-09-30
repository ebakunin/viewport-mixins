# viewport-mixins
SCSS mixins to define the widths of `@media` queries.

## Usage in a SCSS document

```
@include mobile-viewport() {
  .mobile {
    display: block;
  }
}

@include tablet-only-viewport() {
  .tablet {
    display: block;
  }
}
```
(See the associated `example.scss` document.)


## Why not use CSS variables?
CSS variable are defined at the root (`:root`) of the document. However, `@media` is not attached to the document at
all. Conceptually, it is above the document in the hierarchy. Therefore, no variables can be used in `@media` definitions.

The W3C has a [proposal](https://drafts.csswg.org/css-env-1/#issues-index) for a environment variable (`env()`) that would allow variables in media queries. 
As of October 2023, the proposal is still in stage 1 and may never be accepted. 