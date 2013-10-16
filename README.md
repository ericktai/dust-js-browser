dust-js-browser
===============

A sample of using DustJS (non-NodeJS)

I created this repo so that I'd have a reference point on using the DustJS templating library.  The Dust and LinkedIn tutorials didn't really quite describe how to get things running in a regular HTML/JS/Browser app, so this was an exercise in doing so.

# Getting Started

The pre-compiled JS is ready to go - just open `index.html` in the browser and find the template at `src/dusts/todos.dust` to see how DustJS works.

# Dependencies

You'll need `duster.js` to developer. (https://github.com/dmix/dusterjs)   Duster.js will help you compile the templates to JS.  Like SASS/Compass, you can have `duster.js` watch your dusts folder for changes and auto-compile your templates.

Templates are found in `src/dusts` and are compiled to `templates/compiled`.
