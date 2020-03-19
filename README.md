# Simple Sass Bootstrap installation

### Using Parcel package bundler
I prefer using Yarn package manager 

First install the dependencies for Bootstrap and FontAwesome.

```bash
yarn add bootstrap jquery popper.js

yarn add --dev parcel-bundler @fortawesome/fontawesome-free
```

Add Start script to package.json

```json
// package.json
// if necessary add "build": "parcel build ./src/index.html"

"scripts": {
  "start": "parcel ./src/index.html",
  "build": "parcel build ./src/index.html"
}
```
### Customizing Bootstrap styles 
```css
// scss/style.scss

@import '../../node_modules/bootstrap/scss/bootstrap.scss';
```

In JavaScript file to act as the entry point for your app and import any necessary
```javaScript
//  js/script.js

import 'bootstrap'
```
Then, in my index.html file, I add a reference to my Sass and JavaScript entry point.

```html
<!-- index.html -->

<!DOCTYPE html>
<html lang="en">
  <head>
    <link rel="stylesheet" href="scss/style.scss" />
  </head>
  <body>
      <!-- Here 👇 -->
      <script src="js/script.js"></script>
  </body>
</html>
```
### Starts up a development server
parcel will automaticaly handel the sass part.

```bahs
yarn start
````
Done!

### File structure

```html
src
├── js
│   └── script.js
├── scss
│   ├── custom.scss
│   └── style.scss
└── index.html
```
### Global Vaiable Importing
In **custom.scss**, import Bootstrap’s source Sass files.
```css
// Custom.scss
// Option A: Include all of Bootstrap

@import "../node_modules/bootstrap/scss/bootstrap";
```
Two options: include all of Bootstrap, or pick the parts you need.
```css
// Custom.scss
// Option B: Include parts of Bootstrap

// Required
@import "../../node_modules/bootstrap/scss/functions";
@import "../../node_modules/bootstrap/scss/variables";
@import "../../node_modules/bootstrap/scss/mixins";

// Optional
@import "../../node_modules/bootstrap/scss/reboot";
@import "../../node_modules/bootstrap/scss/type";
@import "../../node_modules/bootstrap/scss/images";
@import "../../node_modules/bootstrap/scss/code";
@import "../../node_modules/bootstrap/scss/grid";
```
begin to modify any of the Sass variables and maps in **custom.scss**. the suggest is using the full import stack from our **bootstrap.scss** file as your starting point.
#### Variable defaults
Remove the **!default** flag, when ever overiding variables and overrides must come before imported **Bootstrap’s Sass** files.
```css
// Your variable overrides
$body-bg: #000;
$body-color: #111;

// Bootstrap and its default variables
@import "../node_modules/bootstrap/scss/bootstrap";
```
### Customizing bootstrap Theme
```css
/* -------end customization-------- */
$headings-font-family: Oswald;
$font-family-base: Muli;

$primary: #2f3c48;
$secondary: #6f7f8c;
$success: #3e4d59;
$danger: #cc330d;
$info: #5c8f94;
$warning: #6e9fa5;
$light: #eceeec;
$dark: #1e2b37;

$enable-gradients: true;
$spacer: 0.7rem;
$border-width: 0;
$btn-border-radius: 1.35rem;

// Add SASS theme customizations here..

/* making font responsive */
$font-size-base: 1.8rem;
$embed-responsive-font-size: true;
$rfs-base-font-size: 1rem;

$theme-colors: (
	'primary': $primary,
	'secondary': $secondary,
	'success': $success,
	'danger': $danger,
	'info': $info,
	'warning': $warning,
	'light': $light,
	'dark': $dark,
  
  'spacial': #88ce4f,
	//custom color
);
/* -------end customization-------- */
```

I use for this project for the link [themestr.app for bootstrap](https://themestr.app/)

