## Skcript’s CSS Styleguide - Designing CSS the right way #DesignCode

Skcript uses a very strict mix of LESS and naked CSS for styling amazing UIs for its products. This document includes a variety of styling techniques that would improve the performance, rendering and improvements to the existing as well as new CSS.

The entire framework relies on a custom made Bootstrap, which is tailored for our needs, and everything is very structured class names and meaningful hyphens. This is make sure the code is structured and is organized for any Skcript’s developer to understand and take things forward with ease.

### Naming Conventions

#### Classes and IDs
***Syntax:*** `<purpose>--<sub-purpose> {}`

**Capitalized** with words separated by a **double dash**:

```css
.User--Profile {}
.User--Profile--Name {}
#User--Profile--JS {}
```
Begin the ID or a Class with the purpose. Ex. If you are designing a user profile section of the site, start with User--Profile and append it with the sub classes. If a particular ID or Class is associated with an JavaScript event, append ***JS*** to that particular class.

***Clarification***: Always prefer using classes rather than IDs. Its easier to debug. Use IDs only when you need it for JavaScript actions that are unique to only one div.

#### Classes and IDs for JS
***Syntax:*** `<targetName>--JS`

We have had some pretty terrible experience with handling JavaScript when it comes to handling some classes that we have reused all over the code. The syntax above is the way to use a class that is tied to JS. And make sure the class is exclusive to JS and the styling for that JS event is NOT exclusive to that particular JS class. i.e. DO NOT STYLE THE CLASSES YOU USE FOR JS.

#### Classes, IDs and States
***Syntax:***`<classname>.is<state>`

Sometimes, when you will have to style the CSS according to the state of the element, say a div is now hovered and you need a styling for that, here's how you could handle the styling for particular states:
```css
.User--Profile.isHovered {}
.User--Profile.isActive {}
.User--Profile.isExpanded {}
```

#### Class Reuse - sClasses
***Syntax:*** `sClass--<styling>`

sClasses are also known as special classes. These special classes exists all over the portal. We call the classes like `Stick--To--Right` or `Stick--To--Left` as ***sClasses***. sClass exists to solve two problems. The first is to make maximum reuse of the styling properties and the second is the ability to have a consistent code throughout the site. In programatic terms, these can be called functions.

Begin with **sClass** followed by the **styling** separated by **double dash**
```css
.sClass--Stick--To--Right {}
.sClass--Perfect--Center {}
.sClass--Img--Width-100 {}
```

Here's a real-world example of how this can be used:
```html
<div class="File--Modal--Metadata sClass--Stick--To--Right"> /*We have a File Modal Dialog that is usually center aligned to the screen. And sClass--Stick--To--Right will make it stick to right which has right: 0;*/
   <div class="File--Preview--Thumbnail sClass--Perfect--Center">
      <img src="file-thumbnail.png" class="sClass--Img--Width-100" />
   </div>
</div>
```
#### Images and Icons
***Syntax:*** `<type>-<purpose>.<extension>`

**lowercase** image filenames and begins with a **purpose**
```shell
icon-home.svg
profile-fallback.svg
background-fallback.png
```
**Tip:** If you are using CSS with Rails. Migrate to SCSS with `asset-data-url('image-filename.svg')` instead of using the regular `url('image-filename.svg')`

Always prefer using compressed PNGs for large background images, and SVGs for elements like icons. Icons are usually crafted with [Sketch for Mac](http://bohemiancoding.com/sketch/) with 512x512 dimensions.

#### Modules and Styling
***Syntax:*** `<modulename>--<descendant>`

**Capitalized** name of the module followed by its **descendant** seperated by **double dash**

A lot of the products we create are driven by Modules, and so is the development. All of the CSS Classes that are exclusive to a particular module are named according to that module. Here's an example:

```css
.FileUploads--Name {}
.FolderUploads--Size {}
```

#### Using Variables
***Syntax:***`<property>--<style/value>--<ModuleName>`

Variables are special. We use variables in places where an event occured and there's a necessity to change the styling for that particular element. This example would show you how to create a CSS variable when a color change is required:

```css
.color--skcriptRed--Menu {}
```

#### Colors

Colors are usually handled by a separate CSS file in your project named `endurance`. The `endurance` contains global attributes that can be re-used over and over again, which includes things like the color scheme.

**Note:** Always use **RGB and RGBA** color schemes and NOT HEX.

All the colors are structured in `endurance` alphabatically and with a corresponding hover states or active states that align to the color scheme. This is to make sure its easy for us to debug. And thanks to a ton of pre-processors that are available that will help us minify the CSS and JS files during production.
