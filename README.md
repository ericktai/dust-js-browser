dust-js-browser
===============

A sample of using DustJS (non-NodeJS example)

I created this repo as a reference point on using the DustJS templating library without NodeJS in a "traditional" browser app with script tag inclusions.  The Dust and LinkedIn tutorials didn't really quite describe how to get things running in a regular HTML/JS/Browser app, so this was an exercise in doing so.

# Getting Started

The pre-compiled JS is ready to go - just open `index.html` in the browser and find the template at `src/dusts/todos.dust` to see how DustJS works.

# Dependencies

You'll need `duster.js` to develop. (https://github.com/dmix/dusterjs)   Duster.js will help you compile the templates to JS.  Like SASS/Compass, you can have `duster.js` watch your dusts folder for changes and auto-compile your templates.

Templates are found in `src/dusts` and are compiled to `templates/compiled`.

# How It Works

Save your DustJS templates as `*.dust` files in the `src/dusts` folder.  With `duster.js` running (https://github.com/dmix/dusterjs), your template will be autocompiled.

You can use your template in `index.html` or anywhere you call javascript by calling it by name.  My example dust template is named `todos.dust` so it's referenced by the name `todos`.  The following binds a given JSON (details not shown) to the `todos` template.

```js
dust.render("todos", {
  //This 2nd parameter is the JSON data you want to bind with the template
}, function(err, out) {
  //when done binding the template, the HTML will be represented by the "out" variable
});
```

The template runs against JSON that you pass in.  Here's my JSON data with two `todo` objects:

```js
{
	listname: 'My Todos',
	todos: [
		{
			action: 'learn some dust!',
			duedate: 'tomorrow'
		},
		{
			action: 'visit the south bay',
			duedate: 'tomorrow'
		}
	]
}
```

Combined:

```js
dust.render("todos", {
	listname: 'My Todos',
	todos: [
		{
			action: 'learn some dust!',
			duedate: 'tomorrow'
		},
		{
			action: 'visit the south bay',
			duedate: 'tomorrow'
		}
	]
}, function(err, out) {
  //when done binding the template, the HTML will be represented by the "out" variable
});
```

Finally, the output is handled by the function in the 3rd parameter: `dust.render(..., ..., function(err, out) {})`.  `out` represents the processed HTML result.  To set that to a `div`, simply use something like jQuery to do so:

```js
dust.render("todos", {
	//JSON data...
}, function(err, out) {
  $('#content').html(out);
});
```

## More Information

Read more about DustJS at the LinkedIn Dust Tutorial: https://github.com/linkedin/dustjs/wiki/Dust-Tutorial




