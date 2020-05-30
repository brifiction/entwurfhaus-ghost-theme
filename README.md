# Entwurfhaus Ghost Theme

A Ghost theme, built for the [Entwurfhaus](https://entwurfhaus.com) website. It is using the TailwindCSS, a highly customizable, low-level CSS framework.

# Summary

This template was forked from the [TryGhost/Starter](https://github.com/TryGhost/Starter) resource. The goal is to utilize TailwindCSS, for building a custom Ghost theme.

# Development

## Overview

Styles are compiled using Gulp/PostCSS to polyfill future CSS spec. This project requires:

1. [Node](https://nodejs.org/)
1. [Yarn](https://yarnpkg.com/) 
1. [Gulp](https://gulpjs.com)
1. [TailwindCSS](https://tailwindcss.com)

After that, from the theme's root directory:

```bash
# Install
yarn

# Run build & watch for changes
$ yarn dev
```

Next, edit `/assets/css/` files, which will be compiled to `/assets/built/` automatically.

The `zip` Gulp task packages the theme files into `dist/<theme-name>.zip`, which you can then upload to your site.

```bash
# Run to create a Ghost theme deployment package
yarn zip
```

## Process

1. Using yarn, install the ``ghost-cli`` as below:
    ```bash
    yarn global add ghost-cli@latest
    ```
1. Create a new local Ghost project. For example:
    ```bash
    # Tip: Do not name your project 'ghost'
    mkdir awesome-ghost
    cd awesome-ghost

    # Run the install command, it will automatically start
    ghost install local
    ```
1. If you need to further manage your local ``ghost``, there are some useful commands below:

    ```bash
    # Stop ghost
    ghost stop

    # Start ghost
    ghost start

    # View logs
    ghost log

    # List all running Ghost blogs
    ghost ls
    ```
1. Finally, a simple local development process can be achieved by placing your Ghost theme into the ``themes`` folder, such as ``content\themes\awesome-ghost-theme``. It is from there, using ``yarn dev`` while you're previewing your theme changes on the locally hosted ``awesome-ghost``.    

# Testing

Validating your Ghost theme is handled efficiently with the [GScan tool](https://gscan.ghost.org/). GScan will check your theme for errors, deprecations and compatibility issues. GScan is used in several ways:

1. The [GScan site](https://gscan.ghost.org/) is your first port of call to test any themes that you're building to get a full validation report

1. When a theme is uploaded in Ghost admin, it will automatically be checked with gscan and any fatal errors will prevent the theme from being used

1. gscan is also used as a command line tool

## Command line

To use GScan as a command line tool, globally install the ``gscan`` npm package:

```bash
# Install the npm package
npm install -g gscan

# Use gscan <file path> anywhere to run gscan against a folder
gscan /path/to/ghost/content/themes/casper

# Run gscan on a zip file
gscan -z /path/to/download/theme.zip
```