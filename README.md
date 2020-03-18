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
// if necessary add "build": "parcel build ./src/index.html

"scripts": {
  "start": "parcel ./src/index.html",
  "build": "parcel build ./src/index.html
}
```
### Customizing Bootstrap styles 
```css
// scss/style.scss

@import "~bootstrap/scss/bootstrap";
```

In JavaScript file to act as the entry point for your app and import any necessary
```javaScript
//  js/script.js

import 'bootstrap'
import '@fortawesome/fontawesome-free/css/all.css'
import './style.scss' // Import our scss file
```
Then, in my index.html file, I add a reference to my JavaScript entry point.

```html
<!-- index.html -->

<!DOCTYPE html>
<html lang="en">
  <head>
  </head>
  <body>
      <!-- Here 👇 -->
      <script src="js/script.js"></script>
  </body>
</html>
```
### Starts up a development server 
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
In **custom.scss,** import Bootstrap’s source Sass files.
```css
// Custom.scss
// Option A: Include all of Bootstrap

@import "../node_modules/bootstrap/scss/bootstrap";
```
