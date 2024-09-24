# viewport-mixins
SCSS mixins to define the width of `@media` queries.

## Example usage in a SCSS document
```
.mobile, .tablet-only {
  display: none;
}

@include mobile-viewport() {
  .mobile {
    display: block;
  }
}

@include tablet-only-viewport() {
  .tablet-only {
    display: block;
  }
}
```
(See the associated `example.scss` document)


## Why not use CSS variables?
CSS variable are defined at the root (`:root`) of the document. 
However, `@media` is not attached to the document at all. 
Conceptually, it is above the document in the hierarchy. 
Therefore, no variables can be used in `@media` definitions.

The W3C has a [proposal](https://drafts.csswg.org/css-env-1/#issues-index) for an environment variable (`env()`) that 
 would allow variables in media queries. 
As of August 2024, the proposal is still in stage 1 and may never be implemented. 
