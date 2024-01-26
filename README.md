# Calmaria SPA Project
A project made especially to demonstrate and practice my **SASS** skills

## Preview
Visit this URL to view the page: https://devhelena.github.io/Calmaria-SPA/

## Author
Name: Helena Maia

LinkedIn: https://www.linkedin.com/in/devhelena/

E-mail: helenaaraujo.dev@gmail.com

## About SASS
### Installation
To install SASS use the command `npm install sass`

### Create file
Create a .scss file

### Alignment
Differently from CSS, if you want to style an HTML element that is nested within another in SASS, you can utilize hierarchical nesting to apply styles. For example:
```scss
.parent-element {
  color: blue;

  p {
    font-weight: bold;
  }
}
```
In this example, the `p` is styled in a hierarchical manner within the .parent-element.


### `@extend` in SASS
The `@extend` directive in SASS allows you to share a set of CSS properties from one selector to another, promoting code reusability. It's particularly useful when you have several selectors that share a common set of styles.

To use `@extend`, define a placeholder selector with the desired styles. Then, in other selectors, use `@extend` followed by the placeholder selector.
```scss
// Define a placeholder with common styles
.base-style {
  font-size: 16px;
  color: #333;
}

// Extend the base styles in different selectors
.element1 {
  @extend .base-style;
  font-weight: bold;
}

.element2 {
  @extend .base-style;
  background-color: lightgray;
}

```
In this example, `.base-style` acts as a reusable set of styles. Both `.element1` and `.element2` extend these styles, inheriting the common properties such as font-size and color. This approach reduces redundancy and makes it easier to maintain consistent styles across multiple selectors.


### Variables
Variables in SASS allow you to store values and reuse them throughout your stylesheet. This promotes consistency and makes it easier to update styles globally.

To use variables, declare them with the `$` symbol followed by the variable name and assign a value to it. Later, you can reference the variable wherever you need that value.
```scss
// Declare variables for common colors
$primary-color: #3498db;
$secondary-color: #2ecc71;

// Use variables in styles
.element {
  background-color: $primary-color;
  color: $secondary-color;
}
```
In this example, `$primary-color` and `$secondary-color` are declared as variables storing color values. These variables are then used in the `.element` selector to define the background color and text color. If you later decide to change the color scheme, you can simply update the variable values, and the changes will be reflected throughout the stylesheet.


### `&` in SASS
In SASS, the `&` symbol is a powerful feature that allows you to reference the parent selector within nested contexts. It is commonly used to generate more specific or contextual selectors.
```scss
.button {
  color: #3498db;

  &:hover {
    background-color: #3498db;
  }

  &.active {
    border: 2px solid #3498db;
  }
}
```
- `:hover` Selector:
  
  The `&` allows you to reference the parent `.button` selector within the `:hover` context. This generates a more specific selector: `.button:hover`.
- Class Modification:
  
  The `&` is used with `.active` to create a more specific selector: `.button.active`. This is helpful when styling elements with specific states.

Advanced Usage:
```scss
.panel {
  &.primary {
    background-color: #3498db;

    &-header {
      font-size: 18px;
    }

    &-content {
      padding: 20px;
    }
  }

  &.secondary {
    background-color: #2ecc71;

    &-header,
    &-content {
      color: #fff;
    }
  }
}
```
- Nested Element Selectors:

  The `&` is used to create more specific selectors for different variations of the `.panel component`, such as `.panel.primary` and `.panel.secondary`.
- Element Parts:

  The `&-header` and `&-content` references allow you to generate more specific selectors based on the parent context.

Resulting CSS:
```css
.button {
  color: #3498db;
}

.button:hover {
  background-color: #3498db;
}

.button.active {
  border: 2px solid #3498db;
}

.panel.primary {
  background-color: #3498db;
}

.panel.primary-header {
  font-size: 18px;
}

.panel.primary-content {
  padding: 20px;
}

.panel.secondary {
  background-color: #2ecc71;
}

.panel.secondary-header,
.panel.secondary-content {
  color: #fff;
}
```
The `&` symbol simplifies the process of creating modular and maintainable styles, providing a clear and concise way to generate contextual selectors.


### `@mixins` in SASS
Mixins in SASS allow you to group together a set of styles and reuse them across different selectors. They are particularly useful for encapsulating reusable patterns or complex styles.

To use mixins, define them using the @mixin directive, and then apply them to selectors with the @include directive.
```scss
// Define a mixin for a box-shadow
@mixin box-shadow($color) {
  box-shadow: 0 4px 8px $color;
}

// Use the mixin in different selectors
.element1 {
  @include box-shadow(#3498db);
}

.element2 {
  @include box-shadow(#2ecc71);
}
```

In this example, a mixin named `box-shadow` is defined with a parameter for the shadow color. The mixin is then included in both `.element1` and `.element2` with different shadow colors. This allows you to reuse the same box-shadow style with various color options, promoting code modularity and maintainability.


### Imports with `@use` in SASS
The @use rule in SASS is a modern way of importing styles, mixins, and variables from other files.
```scss
@use '../abstract/variables';
@use '../abstract/mixins';

.element {
  background-color: variables.$primary-color;
  @include mixins.box-shadow(#3498db);
}
```
- The @use rule is used to import specific files, providing a clean and modular structure.
- Imported styles, mixins, and variables are accessed using the namespace of the imported file.

### SASS or SCSS?
SASS provides two syntax options: the original indented syntax (often referred to as SASS) and the newer SCSS (Sassy CSS) syntax. The primary difference lies in their syntax styles.

SASS (Indented Syntax):
```sass
@use '../abstract/variables'
@use '../abstract/mixins'

.element
  background-color: variables.$primary-color
  @include mixins.box-shadow(#3498db)
```
The main distinction lies in the use of `{ }` and `;` as well as the file extension. SASS, with its indented syntax, relies on indentation for block structure and omits semicolons and curly braces. On the other hand, SCSS closely resembles traditional CSS, using semicolons and curly braces for defining blocks. Additionally, SASS files have a `.sass` extension, while SCSS files use the `.scss` extension.

### Compile SCSS/SASS to CSS:
Navigate to the directory containing your SCSS/SASS file and run the following command to compile:

`sass input.scss output.css`

To automatically recompile when changes occur, use the --watch option:

`sass --watch input.scss:output.css`

## Final considerations
For more practical examples on SASS, check out the complete project!

Thank you for reading this far.

Sincerely, Helena Maia :)
