# SCSS Style Guide

Fluid 2 use the SCSS syntax to compile CSS for most of our projects. If you are new to SCSS then please check out the [official documentation](http://sass-lang.com/guide).

## Getting Started

In most situations we use [Gulp](http://gulpjs.com/) to handle SCSS compilation tasks. In the future I will add a sample `gulpfile` to this repository that can be used when starting a new project. For projects built in Laravel 5 a `gulpfile` is provided as part of the initial project structure which can be adapted based on the needs of the project.

## Structuring Projects

Most of our projects use Version 3 of the [Bootstrap](http://getbootstrap.com/) framework to handle responsive functionality and to provide the core UI elements. The starting point for these projects is [Bootstrap SASS](https://github.com/twbs/bootstrap-sass) which is required from [NPM](https://www.npmjs.com/) and then compiled as part of the core CSS file. As much as possible the file structure for any project matches that used by Bootstrap SASS, as does the style of any comments.

#### Project Example

This is taken from a project that is currently in progress I will try and keep it as up to date as possible as the project progresses.

    .
    +-- mixins
    |   +-- _spin_animation.scss
    +-- _buttons.scss
    +-- _mixins.scss
    +-- _utilities.scss
    +-- _variables.scss
    +-- app.scss

###### `app.scss`

This is the entry point to the project. From this file you may **only** import partial files using the `@import` syntax. Below is an example taken from a current project.

    // Core variables and mixins including any overrides for Bootstrap's variables
    @import "variables";
    @import "mixins";

    // Bootstrap
    @import "node_modules/bootstrap-sass/assets/stylesheets/bootstrap";

    @import "buttons";

    // Utilitiy classes
    @import "utilities";

This example does a number of key things. First it imports the `_variables.scss` file. This file declares all of the variables for the project including overrides for any of Bootstrap's default variables which will be determined on a project by project basis. Second it includes the `_mixins.scss` file which in turn will include all the files from the `mixins` directory. Next it imports Bootstrap itself, the specific path for this will depend on where in the project NPM dependencies are installed. Finally it imports all of the project specific custom files. As much as possible these should be split into small self-contained modules reflecting specific elements, element types or pages.

###### `_variables.scss`

The structure of this file should follow Bootstrap's own [variables file](https://github.com/twbs/bootstrap-sass/blob/master/assets/stylesheets/bootstrap/_variables.scss) excluding the `!default` declarations. This file should begin by defining **all** of the colours used in a project as per the example below.

    //
    // Variables
    // --------------------------------------------------


    //== Colours
    //
    //##

    $white:           #ffffff;
    $white-off:       #f7f7f7;

    $black:           #272727;

    $brown-darker:    #312F2F;
    $brown-dark:      #3f3939;

    $blue-dark:       #233944;
    $blue-light:      #d3e0e9;
    $blue-lighter:    #eff4f7;

    $orange:          #fc8602;

    //** Override some of Bootstrap's greys.
    $gray-darker:     #5d5d5d;
    $gray-dark:       #808080;
    $gray:            #9daab0;
    $gray-light:      #e5e5e5;
    $gray-lighter:    #ededed;


    //== Scaffolding
    //
    //##
    
    $text-color: $black;

    //** Global textual link color.
    $link-color: $orange;

    //** Background color for `<body>`.
    $body-bg: $white-off;
