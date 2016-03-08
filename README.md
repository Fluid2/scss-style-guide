# SCSS Style Guide

Fluid 2 use the SCSS syntax to compile CSS for most of our projects. If you are new to SCSS then please check out the [official documentation](http://sass-lang.com/guide).

## Getting Started

In most situations we use [Gulp](http://gulpjs.com/) to handle SCSS compilation tasks. In the future I will add a sample `gulpfile` to this repository that can be used when starting a new project. For projects built in Laravel 5 a `gulpfile` is provided as part of the initial project structure which can be adapted based on the needs of the project.

## Structuring Projects

Most of our projects use Version 3 of the [Bootstrap](http://getbootstrap.com/) framework to handle responsive functionality and to provide the core UI elements. The starting point for these projects is [Bootstrap SASS](https://github.com/twbs/bootstrap-sass) which is required from [NPM](https://www.npmjs.com/) and then compiled as part of the core CSS file. As much as possible the file structure for any project matches that used by Bootstrap SASS, as does the style of any comments.

#### Folder Layout Example
    .
    +-- mixins
    |   +-- _spin_animation.scss
    +-- _buttons.scss
    +-- _mixins.scss
    +-- _utilities.scss
    +-- _variables.scss
    +-- app.scss

###### `app.scss`

This is the entry point to the project. From this file you may **only** import other files from the top level directory using the `@import` syntax.
