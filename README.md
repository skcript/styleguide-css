## Skcript’s CSS Styleguide - Designing CSS the right way #DesignCode

Skcript uses a very strict mix of LESS and naked CSS for styling amazing UIs for its products. This document includes a variety of styling techniques that would improve the performance, rendering and improvements to the existing as well as new CSS.

The entire framework relies on a custom made Bootstrap, which is tailored for our needs, and everything is very structured class names and meaningful hyphens. This is make sure the code is structured and is organized for any Skcript’s developer to understand and take things forward with ease.

### Naming Conventions

#### Classes and IDs
Syntax: `<purpose>--<sub-purpose> {}`
**Capitalized** with words separated by a **double dash**:

```css
.User--Profile {}
.User--Profile--Name {}
#User--Profile--JS {}
```
Begin the ID or a Class with the purpose. Ex. If you are designing a user profile section of the site, start with User--Profile and append it with the sub classes. If a particular ID or Class is associated with an JavaScript event, append ***JS*** to that particular class.

***Clarification***: Always prefer using classes rather than IDs. Its easier to debug. Use IDs only when you need it for JavaScript actions that are unique to only one div.

#### Classes and IDs for JS
Syntax: `<targetName>--JS`

We have had some pretty terrible experience with handling JavaScript when it comes to handling some classes that we have reused all over the code. The syntax above is the way to use a class that is tied to JS. And make sure the class is exclusive to JS and the styling for that JS event is NOT exclusive to that particular JS class. i.e. DO NOT STYLE THE CLASSES YOU USE FOR JS.

#### Images and Icons
Syntax: `<type>-<purpose>.<extension>`
**lowercase** image filenames and begins with a **purpose**
```shell
icon-home.svg
profile-fallback.svg
background-fallback.png
```
**Tip:** If you are using CSS with Rails. Migrate to SCSS with `asset-data-url('image-filename.svg')` instead of using the regular `url('image-filename.svg')`
