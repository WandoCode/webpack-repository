# Webpack boilerplate

This repo contains a basic implementation of a project with Webpack.

## index.html

The `index.html` file on the root of the project: it can be used for developpement.

When the website is built, the HTMLWebpackPlugin will make a copy of it in the `/dist` folder and inject what is usefull:

- a script tag linked to the built JS
- a link tag for the generated CSS

## `./dist`

It contains the built project that can be used for production.

## Scripts

### `start:dev`

This script use the webpack-dev-server to launch a devloppement server.

The HMR is enabled to re-build the project quickly and reload the page.

### `watch`

This script just rebuild quickly the project whang a modification is detected.

### `build`

This script makes a proper production build.

## Style

At build, the mini-css-extract-plugin will create a separate CSS file in `/dist` containing all the CSS.

The CSS file have to be importated at the begining of `index.js`

### SASS

To use SASS:
`npm install -D sass sass-loader`

To bundle SASS to CSS with webpack, uncomment the sass part in `webpack.config.js`. In that case, the SCSS file have to be imported into hte `index.js` file.

Add the following script to simply compiles SASS into CSS:`"build:sass" : "sass ./src/style/index.scss ./dist/style/index.css"`

## Assets

At build, webpack will create a separate folder `/assets` containing all the assets used in the project.

Assets have to be imported into JS file and set as .src of the img tag.
