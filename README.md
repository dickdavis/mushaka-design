# Mushaka Design

## Table of Contents
* About
* Getting Started
    * Installation
    * Usage
* Contributing
    * Code Style
    * Building
    * Releases

## About
This project is a design framework used by Mushaka Solutions. It provides buttons, cards, links, heros, and more.

## Getting Started
### Installation
To use the design components in your project, install with `yarn add mushaka-design` (or `npm install mushaka-design`).

Then, include the assets in your main scss file above any custom stylesheets.

```
@import "mushaka-design/src/main";
```

### Usage
Reference the included docs for information on using components, mixins, or utilities.

Variables are used heavily throughout the library, and you can override these variables to adjust the styles to your project's needs. Reference the `src/base/_variables.scss` file for a complete listing of the variables used.

## Contributing
### Code Style

For Javascript, we use ESLint with the Standard rules. To run the linter, execute:
```
eslint app/assets/javascripts
```

For stylesheets, we use Stylelint. To run the linter, execute:
```
stylelint app/assets/stylesheets
```

### Building

### Releases
