# Mushaka Design

## Table of Contents
* About
* Installation
* Usage
* License Notice

## About
This project is a design framework used by Mushaka Solutions. It provides buttons, cards, links, heros, and more.

## Installation
To use the design components in your project, install with `yarn add mushaka-design` (or `npm install mushaka-design`).

Then, include the assets in your main scss file above any custom stylesheets and below any theme overrides.

```
@import "mushaka-design/src/main";
```

## Usage
Reference the included docs for information on using components, mixins, or utilities. You may build the docs using command `yarn docs`, which will generate documentation in HTML in the `docs/` directory. Examples are included for each component, placeholder, mixin, function, and variable.

Variables and maps are used heavily throughout the library, and you can override these variables to adjust the styles to your project's needs. Reference the `src/base/variables.scss` file for a complete listing of the variables used. Listed below is an example of how an app that uses this library can override the standard system font stack:

```
@font-face {
  font-family: 'open_sansregular';
  src: asset-url('OpenSans-Regular-webfont.eot');
  src:
    asset-url('OpenSans-Regular-webfont.eot?#iefix') format('embedded-opentype'),
    asset-url('OpenSans-Regular-webfont.woff') format('woff'),
    asset-url('OpenSans-Regular-webfont.ttf') format('truetype'),
    asset-url('OpenSans-Regular-webfont.svg#open_sansregular') format('svg');
  font-weight: normal;
  font-style: normal;
}

@font-face {
  font-family: 'poppinsbold';
  src:
    asset-url('poppins-bold-webfont.woff2') format('woff2'),
    asset-url('poppins-bold-webfont.woff') format('woff');
  font-weight: normal;
  font-style: normal;
}

@font-face {
  font-family: 'poppinsregular';
  src:
    asset-url('poppins-regular-webfont.woff2') format('woff2'),
    asset-url('poppins-regular-webfont.woff') format('woff');
  font-weight: normal;
  font-style: normal;
}

@font-face {
  font-family: 'poppinssemibold';
  src:
    asset-url('poppins-semibold-webfont.woff2') format('woff2'),
    asset-url('poppins-semibold-webfont.woff') format('woff');
  font-weight: normal;
  font-style: normal;
}

$base-font-family: 'open_sansregular';
$heading-bold-font-family: 'poppinsbold';
$heading-semibold-font-family: 'poppinssemibold';
$heading-regular-font-family: 'poppinsregular';

@import "mushaka-design/src/main";
```

Similarly, you can override any of the variables/maps contained within `src/base/variables.scss` by providing the override values before importing the project's stylesheets.

## License Notice
Copyright 2019 Mushaka Solutions, Inc.

mushaka-design is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

mushaka-design is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with. If not, see http://www.gnu.org/licenses/.
