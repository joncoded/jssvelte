# jssvelte

a gathering of svelte stuff

## setup

```
git clone https://github.com/joncoded/jssvelte.git
npm install
npm run dev
```

- a page will load on `http://localhost:5173`
- edit files inside of `src/lib/` and `src/App.svelte` to change the app

## app index

- a navigator for all the app components when the aforementioned page loads

## app components

- add a new component by creating a subfolder in `src/lib/` (e.g. `SomeApp`) and calling the file `SomeApp.svelte`
  - i.e. the same name as the folder but with `.svelte` at the end
- to add new components to the app navigation, update `src/lib/index.js` (simple as!)

### component with internal CSS

```html
<script>
  // javascript
</script>

<!-- html goes here -->

<style>
/* css can go here on in an external file imported by javascript */
</style>
```

### component with external CSS

```html
<script>
  // javascript
  import './style.css';
</script>

<!-- html goes here -->
```

(create a separate `style.css` for the CSS)

## component samples

* **ColorSlider** (generate a hex code by using sliders)
* **FontSlider** (increase a font size with a slider)
* **ExpandingSquare** (animation using setInterval and variables)
* **KeyEventSquare** (user interactivity using key bindings)
* **Multiplier** (reactive variables in input fields)