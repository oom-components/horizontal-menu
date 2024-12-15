# Horizontal menu

Web component to create a responsive horizontal menu. In narrow screens, the
items that don't fit in the menu are moved to a dropdown list.

- No dependencies
- Light: Less than 200 lines of code (including comments and spaces)
- Follow the **progressive enhancement strategy**. If the JavaScript fails, the
  links are visible.
- No styles or themes are provided with this package. Just the basic styles.
- Build with modern javascript, using ES6 modules and custom elements
- Live demo: https://oom-components.github.io/horizontal-menu/demo

## Usage

### HTML

Create the menu with the following HTML code:

```html
<my-menu>
  <a href="#1">Link 1</a>
  <a href="#2">Link 2</a>
  <a href="#3">Link 3</a>
  <a href="#4">Link 4</a>
  <a href="#5">Link 5</a>
</my-menu>
```

### JS

Register the custom element to make it responsive:

```js
import Menu from "horizontal-menu/src/menu.js";

// Define the custom element
customElements.define("my-menu", Menu);
```

### CSS

Use CSS to customize your menu. This web component uses a shadow dom and _parts_
to customize the internal elements. The internal tree is (removed some
attributes for clarity):

```html
<div part="menu">
  <div part="links">
    <!-- Horizontal links -->
  </div>
  <div part="dropdown">
    <button part="dropdown-button">
      <!-- Button to show/hide the hidden links -->
    </button>
    <div part="dropdown-links">
      <!-- Hidden links -->
    </div>
  </div>
</div>
```

```css
my-menu {
  /* Generic styles */

  &::part(menu) {
    /* Main container */
  }
  &::part(links) {
    /* Horizontal links */
  }
  &::part(dropdown) {
    /* Dropdown container */
  }
  &::part(dropdown-button) {
    /* Button to show/hide the dropdown */
  }
  &::part(dropdown-links) {
    /* Dropdown links */
  }
}
```
