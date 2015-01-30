## Skcript’s CSS Styleguide - Designing CSS the right way #DesignCode

Skcript uses a very strict mix of LESS and naked CSS for styling amazing UIs for its products. This document includes a variety of styling techniques that would improve the performance, rendering and improvements to the existing as well as new CSS.

The entire framework relies on a custom made Bootstrap, which is tailored for our needs, and everything is very structured class names and meaningful hyphens. This is make sure the code is structured and is organized for any Skcript’s developer to understand and take things forward with ease. 

### Naming Conventions 
Classes and IDs are Capitalized with words separated by a double dash:

```css
.user-profile {}
.post-header {}
#top-navigation {}
```