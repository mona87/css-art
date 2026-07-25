# CSS Image — Flat Design vs Skeuomorphism

A single-page, pure CSS/Sass illustration of a Mario-style character head that
toggles between two rendering styles — **flat design** and **skeuomorphism**
— when clicked. The toggle itself is a plain HTML checkbox + `:checked ~`
selector, so no JavaScript is required for the core effect.

## Preview

Open `dist/index.html` in a browser and click anywhere on the illustration
to switch between the flat and skeuomorphic looks.

## Project structure

```
css-art/
├── dist/                 # Built, browser-ready output
│   ├── index.html
│   ├── style.css          # Compiled from src/style.scss
│   └── style.css.map
└── src/                   # Editable source
    ├── style.scss          # Entry point — composes the partials below
    └── styles/
        ├── _variables.scss     # Color palette + font import
        ├── _placeholders.scss  # Shared %pos / %text placeholder selectors
        ├── _base.scss          # body, label, title, instructions
        ├── _flat.scss          # Flat-design character shapes
        └── _skeuomorphic.scss  # input:checked ~ .luigi overrides
```

## Building

Requires the Dart Sass compiler (used here via `npx`, no install needed):

```bash
npx sass src/style.scss dist/style.css
```

To rebuild automatically while editing:

```bash
npx sass --watch src/style.scss:dist/style.css
```

Then open `dist/index.html` in a browser to view the result.

## Tech

- HTML — single element tree, styled entirely with pseudo-elements
- Sass (SCSS) — modular partials, `%placeholder` selectors, `@extend`
- No JavaScript, no build tooling beyond the Sass compiler
