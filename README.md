
# UnitSold Maxima Pages

This is a playground to implement and preview the Oberoi Maxima presentation.

The presentation will be used in a bigger project, with a more complex build environment so these pages have to be lightweight. We provided a quick and dirty framework that should be enough to implement everything.

## Important

> Do NOT modify package.json. If you really need anything extra, ask. This is just a simplified environment so you can start building. The result will be part of a larger project, which is not linked here.

- Do NOT use any CSS frameworks (e.g. Bootstrap, Tailwind, etc), we need a clean CSS solution with human identifiable id/class names
- Use the HTML files provided to create the page layouts
- We provide the JavaScript framework. You can add utility/helper functions as needed

## Getting Started

The project uses Node v14+, and Snowpack for quick iteration, with SASS/SCSS support.

> Run `npm i` in the project folder to install the dependencies.

> The live server can be started with `npm start`.

## Folder structure

- `/public` contains the static files, and here are the HTML files to use.
- `/src` contains the files that need any build steps
  - `css` can contain files with SCSS syntax
  - `scripts` JavaScript files
  - it's OK to create extra files and `@import` them if needed

## Implementation

There is a desktop version and a mobile version of the presentation with different behavior.

### Desktop

The desktop version can be paged through like a slideshow. The page transitions are handled via [Highway.js](https://highway.js.org/) and [GSAP](https://greensock.com/).

The desktop pages are separated into html files each, and named like in the Figma document (e.g. `public/Amenities01.html`). The one exception is the Intro page, which is named `public/index.html`. There is also `public/_desktopTemplate.html`, which contains a skeleton template, if needed.

Styling is separated into 2 files:

- `src/css/brand.css` should contain CSS reset, typography, custom attributes; basically it should be easy to change the presentation look and feel by just changing some parameters here
- `src/css/layout.css` should contain all the separate page layouts

I have created a basic setup in `src/scripts/script.js`, and added some transition examples in `src/scripts/transitions/`, but you can change any of it as you see fit.

### Mobile

The mobile version is basically a vertical scrolling website, no paging mechanism, you can just layout the pages after each other according to the Figma document.

The mobile version should be implemented in `public/_mobile.html`.

- `src/css/brand_m.css` should contain any setup that is different from the desktop version, e.g.: font sizing
- `src/css/layout_m.css` should contain layouting for everything on the page

There are GSAP ScrollTrigger-based transitions and I have created an example setup in `src/scripts/script_m.js`. You can also change this as needed.

## Good luck

If you have any questions/concerns, ask away!
