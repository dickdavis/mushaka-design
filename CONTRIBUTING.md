# Contributing

## Table of Contents
* Style
* Documentation
* Building
* Releasing

## Style
For stylesheets, we use Stylelint with the stylelint-config-standard rules. To run the linter, execute:

```
yarn lint
```

This will run the linter on all of the stylesheets, fixing what it can automatically and outputting errors for the rest.

### Releases
Releases are managed by the code maintainer and require appropriate permissions and access to the NPM package and GitLab repository. To initiate the release process, execute:

```
yarn release
```

Given that the release process automatically generates a CHANGELOG based on commit history, you must follow the guidelines for commit messages.

For the first line of your commit, please include the nature of the change that you are introducing in a tag prefix, followed by a concise summary of those changes.

Format: `Tag: Concise summary of the change`

For tags, please use your best judgement to select from the list below in choosing a tag for your commit.

* New - a new feature.
* Fix - a bug fix.
* Update - a change that is backwards compatible.
* Breaking - a change that is not backwards compatible.
* Docs - a change to the project documentation.
* Build - a build process change.
* Upgrade - an upgrade of the project's dependencies.
* Chore - any change that is not user facing that doesn't fit into the above categories.

Example: `Docs: Update CONTRIBUTING.md to include documentation standards`

Please note that we will reject commits that do not adhere to this standard.

## Documentation
You must document any changes or additions to the stylesheets following the [SassDoc](http://sassdoc.com/) conventions. Please refer to the included examples for doucmenting placeholders, mixins, functions, variables, and classes.

An example documentation comment for a placeholder:

```
/// Provides styles for borders.
/// @group base
/// @author Richard Davis
/// @example
///   @extend %default-border-styling;
```

An example documentation comment for a mixin:

```
/// Provides responsive font scaling for headings.
/// @group base
/// @author Richard Davis
/// @param {Number} $_font_scale - The factor by which to scale the font size
/// @example
///   @include heading-font-size(2);
```

An example documentation comment for a function:

```
/// Returns viewport size from $viewport-sizes map for provided key.
/// @group base
/// @author Richard Davis
/// @param {String} $_key - The key to return an associated viewport size for.
/// @example
///   viewport-size("M");
```

An example documentation comment for a variable:

```
/// Viewport sizes
```

An example documentation comment for a class:

```
/// Provides styles for the ButtonGroup element.
/// @group buttons
/// @author Richard Davis
/// @example
///   // A button group with several buttons
///   <div class="ButtonGroup">
///     <button class="Button--solid-safe">Lorem Ipsum</button>
///     <button class="Button--solid-danger">Lorem Ipsum</button>
///   </div>
```

You may build the documentation by executing:

```
yarn docs
```

## Building
To build the project manually, execute:

```
yarn build
```

This compiles the stylesheets into a single CSS stylesheet in the `dist/` directory. To facilitate previewing components as you work on them, you may create an HTML file in the `dist/` directory that loads the built stylesheet. An example file is included here for your convenience; you may need to add elements to test any new/missing components.

```
<html>
  <head>
    <title>Component Preview</title>
    <link rel="stylesheet" href="main.css" />
  </head>
  <body>
		<h2>A plain card</h2>
		<div class="Card">
			<div class="Card__body">
				<p class="Card__body-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Hunc vos beatum; Quamquam te quidem video minime esse deterritum. Ita prorsus, inquam; Non risu potius quam oratione eiciendum?</p>
				<p class="Card__body-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Hunc vos beatum; Quamquam te quidem video minime esse deterritum. Ita prorsus, inquam; Non risu potius quam oratione eiciendum?</p>
				<p class="Card__body-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Hunc vos beatum; Quamquam te quidem video minime esse deterritum. Ita prorsus, inquam; Non risu potius quam oratione eiciendum?</p>
			</div>
		</div>

		<h2>A medium-sized card</h2>
		<div class="Card Card--medium">
			<div class="Card__body">
				<p class="Card__body-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Hunc vos beatum; Quamquam te quidem video minime esse deterritum. Ita prorsus, inquam; Non risu potius quam oratione eiciendum?</p>
				<p class="Card__body-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Hunc vos beatum; Quamquam te quidem video minime esse deterritum. Ita prorsus, inquam; Non risu potius quam oratione eiciendum?</p>
				<p class="Card__body-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Hunc vos beatum; Quamquam te quidem video minime esse deterritum. Ita prorsus, inquam; Non risu potius quam oratione eiciendum?</p>
			</div>
		</div>

		<h2>A small-sized card</h2>
		<div class="Card Card--small">
			<div class="Card__body">
				<p class="Card__body-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Hunc vos beatum; Quamquam te quidem video minime esse deterritum. Ita prorsus, inquam; Non risu potius quam oratione eiciendum?</p>
				<p class="Card__body-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Hunc vos beatum; Quamquam te quidem video minime esse deterritum. Ita prorsus, inquam; Non risu potius quam oratione eiciendum?</p>
				<p class="Card__body-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Hunc vos beatum; Quamquam te quidem video minime esse deterritum. Ita prorsus, inquam; Non risu potius quam oratione eiciendum?</p>
			</div>
		</div>

		<h2>A card with a thick top border</h2>
		<div class="Card--topBorder">
			<div class="Card__body">
				<p class="Card__body-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Hunc vos beatum; Quamquam te quidem video minime esse deterritum. Ita prorsus, inquam; Non risu potius quam oratione eiciendum?</p>
				<p class="Card__body-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Hunc vos beatum; Quamquam te quidem video minime esse deterritum. Ita prorsus, inquam; Non risu potius quam oratione eiciendum?</p>
				<p class="Card__body-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Hunc vos beatum; Quamquam te quidem video minime esse deterritum. Ita prorsus, inquam; Non risu potius quam oratione eiciendum?</p>
			</div>
		</div>

		<h2>A card with a thick right border</h2>
		<div class="Card--rightBorder">
			<div class="Card__body">
				<p class="Card__body-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Hunc vos beatum; Quamquam te quidem video minime esse deterritum. Ita prorsus, inquam; Non risu potius quam oratione eiciendum?</p>
				<p class="Card__body-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Hunc vos beatum; Quamquam te quidem video minime esse deterritum. Ita prorsus, inquam; Non risu potius quam oratione eiciendum?</p>
				<p class="Card__body-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Hunc vos beatum; Quamquam te quidem video minime esse deterritum. Ita prorsus, inquam; Non risu potius quam oratione eiciendum?</p>
			</div>
		</div>

		<h2>A card with a thick bottom border</h2>
		<div class="Card--bottomBorder">
			<div class="Card__body">
				<p class="Card__body-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Hunc vos beatum; Quamquam te quidem video minime esse deterritum. Ita prorsus, inquam; Non risu potius quam oratione eiciendum?</p>
				<p class="Card__body-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Hunc vos beatum; Quamquam te quidem video minime esse deterritum. Ita prorsus, inquam; Non risu potius quam oratione eiciendum?</p>
				<p class="Card__body-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Hunc vos beatum; Quamquam te quidem video minime esse deterritum. Ita prorsus, inquam; Non risu potius quam oratione eiciendum?</p>
			</div>
		</div>

		<h2>A card with a thick left border</h2>
		<div class="Card--leftBorder">
			<div class="Card__body">
				<p class="Card__body-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Hunc vos beatum; Quamquam te quidem video minime esse deterritum. Ita prorsus, inquam; Non risu potius quam oratione eiciendum?</p>
				<p class="Card__body-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Hunc vos beatum; Quamquam te quidem video minime esse deterritum. Ita prorsus, inquam; Non risu potius quam oratione eiciendum?</p>
				<p class="Card__body-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Hunc vos beatum; Quamquam te quidem video minime esse deterritum. Ita prorsus, inquam; Non risu potius quam oratione eiciendum?</p>
			</div>
		</div>

		<h2>A card with a card header and header text</h2>
		<div class="Card">
			<div class="Card__header">
				<p class="Card__header-text">Lorem Ipsum</p>
			</div>
			<div class="Card__body">
				<p class="Card__body-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Hunc vos beatum; Quamquam te quidem video minime esse deterritum. Ita prorsus, inquam; Non risu potius quam oratione eiciendum?</p>
				<p class="Card__body-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Hunc vos beatum; Quamquam te quidem video minime esse deterritum. Ita prorsus, inquam; Non risu potius quam oratione eiciendum?</p>
				<p class="Card__body-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Hunc vos beatum; Quamquam te quidem video minime esse deterritum. Ita prorsus, inquam; Non risu potius quam oratione eiciendum?</p>
			</div>
		</div>

		<h2>A card with a card body and title</h2>
		<div class="Card">
			<div class="Card__body">
				<h2 class="Card__title">Lorem Ipsum</h2>
				<p class="Card__body-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Hunc vos beatum; Quamquam te quidem video minime esse deterritum. Ita prorsus, inquam; Non risu potius quam oratione eiciendum?</p>
				<p class="Card__body-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Hunc vos beatum; Quamquam te quidem video minime esse deterritum. Ita prorsus, inquam; Non risu potius quam oratione eiciendum?</p>
				<p class="Card__body-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Hunc vos beatum; Quamquam te quidem video minime esse deterritum. Ita prorsus, inquam; Non risu potius quam oratione eiciendum?</p>
			</div>
		</div>

		<h2>A card with a card body and spaced title</h2>
		<div class="Card">
			<div class="Card__body">
				<h2 class="Card__title--spaced">Lorem Ipsum</h2>
				<p class="Card__body-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Hunc vos beatum; Quamquam te quidem video minime esse deterritum. Ita prorsus, inquam; Non risu potius quam oratione eiciendum?</p>
				<p class="Card__body-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Hunc vos beatum; Quamquam te quidem video minime esse deterritum. Ita prorsus, inquam; Non risu potius quam oratione eiciendum?</p>
				<p class="Card__body-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Hunc vos beatum; Quamquam te quidem video minime esse deterritum. Ita prorsus, inquam; Non risu potius quam oratione eiciendum?</p>
			</div>
		</div>

		<h2>A card with a card footer and footer text</h2>
		<div class="Card">
			<div class="Card__body">
				<p class="Card__body-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Hunc vos beatum; Quamquam te quidem video minime esse deterritum. Ita prorsus, inquam; Non risu potius quam oratione eiciendum?</p>
				<p class="Card__body-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Hunc vos beatum; Quamquam te quidem video minime esse deterritum. Ita prorsus, inquam; Non risu potius quam oratione eiciendum?</p>
				<p class="Card__body-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Hunc vos beatum; Quamquam te quidem video minime esse deterritum. Ita prorsus, inquam; Non risu potius quam oratione eiciendum?</p>
			</div>
			<div class="Card__footer">
				<p class="Card__footer-text">Lorem Ipsum</p>
			</div>
		</div>

		<h2>A card with a card header, body, title, and footer</h2>
		<div class="Card">
			<div class="Card__header">
				<p class="Card__header-text">Lorem Ipsum</p>
			</div>
			<div class="Card__body">
				<h2 class="Card__title">Lorem Ipsum</h2>
				<p class="Card__body-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Hunc vos beatum; Quamquam te quidem video minime esse deterritum. Ita prorsus, inquam; Non risu potius quam oratione eiciendum?</p>
				<p class="Card__body-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Hunc vos beatum; Quamquam te quidem video minime esse deterritum. Ita prorsus, inquam; Non risu potius quam oratione eiciendum?</p>
				<p class="Card__body-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Hunc vos beatum; Quamquam te quidem video minime esse deterritum. Ita prorsus, inquam; Non risu potius quam oratione eiciendum?</p>
			</div>
			<div class="Card__footer">
				<p class="Card__footer-text">Lorem Ipsum</p>
			</div>
		</div>

		<h2>A card deck with multiple small cards</h2>
		<div class="CardDeck">
			<div class="Card Card--small">
				<div class="Card__body">
					<p class="Card__body-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Hunc vos beatum; Quamquam te quidem video minime esse deterritum. Ita prorsus, inquam; Non risu potius quam oratione eiciendum?</p>
					<p class="Card__body-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Hunc vos beatum; Quamquam te quidem video minime esse deterritum. Ita prorsus, inquam; Non risu potius quam oratione eiciendum?</p>
					<p class="Card__body-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Hunc vos beatum; Quamquam te quidem video minime esse deterritum. Ita prorsus, inquam; Non risu potius quam oratione eiciendum?</p>
				</div>
			</div>
			<div class="Card Card--small">
				<div class="Card__body">
					<p class="Card__body-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Hunc vos beatum; Quamquam te quidem video minime esse deterritum. Ita prorsus, inquam; Non risu potius quam oratione eiciendum?</p>
					<p class="Card__body-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Hunc vos beatum; Quamquam te quidem video minime esse deterritum. Ita prorsus, inquam; Non risu potius quam oratione eiciendum?</p>
					<p class="Card__body-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Hunc vos beatum; Quamquam te quidem video minime esse deterritum. Ita prorsus, inquam; Non risu potius quam oratione eiciendum?</p>
				</div>
			</div>
			<div class="Card Card--small">
				<div class="Card__body">
					<p class="Card__body-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Hunc vos beatum; Quamquam te quidem video minime esse deterritum. Ita prorsus, inquam; Non risu potius quam oratione eiciendum?</p>
					<p class="Card__body-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Hunc vos beatum; Quamquam te quidem video minime esse deterritum. Ita prorsus, inquam; Non risu potius quam oratione eiciendum?</p>
					<p class="Card__body-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Hunc vos beatum; Quamquam te quidem video minime esse deterritum. Ita prorsus, inquam; Non risu potius quam oratione eiciendum?</p>
				</div>
			</div>
    </div>
    <h2>ContentWrapper</h2>
    <div class="ContentWrapper">
      <h1>Title</h1>
      <h2>Subheading Level 2</h2>
      <h3>Subheading Level 3</h3>
      <h4>Subheading Level 4</h4>
      <h5>Subheading Level 5</h5>
      <p>Nemo igitur esse beatus potest. Quod ea non occurrentia fingunt, vincunt Aristonem; Recte, inquit, intellegis. Qui-vere falsone, quaerere mittimus-dicitur oculis se privasse; Quonam, inquit, modo? Quod cum dixissent, ille contra. Non quam nostram quidem, inquit Pomponius iocans;</p>
      <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed ille, ut dixi, vitiose. Falli igitur possumus. Duo Reges: constructio interrete. Tamen a proposito, inquam, aberramus. Hoc loco tenere se Triarius non potuit.</p>
      <code>
        puts "Hello World
      </code>
      <p>ALIO MODO. Atqui reperies, inquit, in hoc quidem pertinacem; Verum hoc idem saepe faciamus. Multoque hoc melius nos veriusque quam Stoici. Pugnant Stoici cum Peripateticis. Itaque contra est, ac dicitis; Itaque contra est, ac dicitis;</p>
      <blockquote>
        <p>ALIO MODO. Atqui reperies, inquit, in hoc quidem pertinacem; Verum hoc idem saepe faciamus. Multoque hoc melius nos veriusque quam Stoici. Pugnant Stoici cum Peripateticis. Itaque contra est, ac dicitis; Itaque contra est, ac dicitis;</p>
      </blockquote>
      <p>ALIO MODO. Atqui reperies, inquit, in hoc quidem pertinacem; Verum hoc idem saepe faciamus. Multoque hoc melius nos veriusque quam Stoici. Pugnant Stoici cum Peripateticis. Itaque contra est, ac dicitis; Itaque contra est, ac dicitis;</p>
      <ul>
        <li>Lorem ipsum</li>
        <li>Lorem ipsum</li>
        <li>Lorem ipsum</li>
      </ul>
      <p>ALIO MODO. Atqui reperies, inquit, in hoc quidem pertinacem; Verum hoc idem saepe faciamus. Multoque hoc melius nos veriusque quam Stoici. Pugnant Stoici cum Peripateticis. Itaque contra est, ac dicitis; Itaque contra est, ac dicitis;</p>
      <ol>
        <li>Lorem ipsum</li>
        <li>Lorem ipsum</li>
        <li>Lorem ipsum</li>
      </ol>
    </div>
    <h2>ContentWrapper nested in a card</h2>
    <div class="Card">
      <div class="Card__body">
        <h2 class="Card__title">Lorem Ipsum</h2>
        <div class="ContentWrapper">
          <h1>Title</h1>
          <h2>Subheading Level 2</h2>
          <h3>Subheading Level 3</h3>
          <h4>Subheading Level 4</h4>
          <h5>Subheading Level 5</h5>
          <p>Nemo igitur esse beatus potest. Quod ea non occurrentia fingunt, vincunt Aristonem; Recte, inquit, intellegis. Qui-vere falsone, quaerere mittimus-dicitur oculis se privasse; Quonam, inquit, modo? Quod cum dixissent, ille contra. Non quam nostram quidem, inquit Pomponius iocans;</p>
          <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed ille, ut dixi, vitiose. Falli igitur possumus. Duo Reges: constructio interrete. Tamen a proposito, inquam, aberramus. Hoc loco tenere se Triarius non potuit.</p>
          <code>
            puts "Hello World
          </code>
          <p>ALIO MODO. Atqui reperies, inquit, in hoc quidem pertinacem; Verum hoc idem saepe faciamus. Multoque hoc melius nos veriusque quam Stoici. Pugnant Stoici cum Peripateticis. Itaque contra est, ac dicitis; Itaque contra est, ac dicitis;</p>
          <blockquote>
            <p>ALIO MODO. Atqui reperies, inquit, in hoc quidem pertinacem; Verum hoc idem saepe faciamus. Multoque hoc melius nos veriusque quam Stoici. Pugnant Stoici cum Peripateticis. Itaque contra est, ac dicitis; Itaque contra est, ac dicitis;</p>
          </blockquote>
          <p>ALIO MODO. Atqui reperies, inquit, in hoc quidem pertinacem; Verum hoc idem saepe faciamus. Multoque hoc melius nos veriusque quam Stoici. Pugnant Stoici cum Peripateticis. Itaque contra est, ac dicitis; Itaque contra est, ac dicitis;</p>
          <ul>
            <li>Lorem ipsum</li>
            <li>Lorem ipsum</li>
            <li>Lorem ipsum</li>
          </ul>
          <p>ALIO MODO. Atqui reperies, inquit, in hoc quidem pertinacem; Verum hoc idem saepe faciamus. Multoque hoc melius nos veriusque quam Stoici. Pugnant Stoici cum Peripateticis. Itaque contra est, ac dicitis; Itaque contra est, ac dicitis;</p>
          <ol>
            <li>Lorem ipsum</li>
            <li>Lorem ipsum</li>
            <li>Lorem ipsum</li>
          </ol>
        </div>
      </div>
    </div>
    <h2>ContentWrapper with a set max width</h2>
    <div class="ContentWrapper--restricted">
      <h1>Title</h1>
      <h2>Subheading Level 2</h2>
      <h3>Subheading Level 3</h3>
      <h4>Subheading Level 4</h4>
      <h5>Subheading Level 5</h5>
      <p>Nemo igitur esse beatus potest. Quod ea non occurrentia fingunt, vincunt Aristonem; Recte, inquit, intellegis. Qui-vere falsone, quaerere mittimus-dicitur oculis se privasse; Quonam, inquit, modo? Quod cum dixissent, ille contra. Non quam nostram quidem, inquit Pomponius iocans;</p>
      <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed ille, ut dixi, vitiose. Falli igitur possumus. Duo Reges: constructio interrete. Tamen a proposito, inquam, aberramus. Hoc loco tenere se Triarius non potuit.</p>
      <code>
        puts "Hello World
      </code>
      <p>ALIO MODO. Atqui reperies, inquit, in hoc quidem pertinacem; Verum hoc idem saepe faciamus. Multoque hoc melius nos veriusque quam Stoici. Pugnant Stoici cum Peripateticis. Itaque contra est, ac dicitis; Itaque contra est, ac dicitis;</p>
      <blockquote>
        <p>ALIO MODO. Atqui reperies, inquit, in hoc quidem pertinacem; Verum hoc idem saepe faciamus. Multoque hoc melius nos veriusque quam Stoici. Pugnant Stoici cum Peripateticis. Itaque contra est, ac dicitis; Itaque contra est, ac dicitis;</p>
      </blockquote>
      <p>ALIO MODO. Atqui reperies, inquit, in hoc quidem pertinacem; Verum hoc idem saepe faciamus. Multoque hoc melius nos veriusque quam Stoici. Pugnant Stoici cum Peripateticis. Itaque contra est, ac dicitis; Itaque contra est, ac dicitis;</p>
      <ul>
        <li>Lorem ipsum</li>
        <li>Lorem ipsum</li>
        <li>Lorem ipsum</li>
      </ul>
      <p>ALIO MODO. Atqui reperies, inquit, in hoc quidem pertinacem; Verum hoc idem saepe faciamus. Multoque hoc melius nos veriusque quam Stoici. Pugnant Stoici cum Peripateticis. Itaque contra est, ac dicitis; Itaque contra est, ac dicitis;</p>
      <ol>
        <li>Lorem ipsum</li>
        <li>Lorem ipsum</li>
        <li>Lorem ipsum</li>
      </ol>
    </div>
    <h2>A hero</h2>
    <div class="Hero">
      <h1 class="Hero__headline">Lorem Ipsum Heading</h1>
      <p class="Hero__lede">Atqui reperies, inquit, in hoc quidem pertinacem; Verum hoc idem saepe faciamus.</p>
    </div>
    <h2>An inverted hero</h2>
    <div class="Hero--inverted">
      <h1 class="Hero__headline">Lorem Ipsum Heading</h1>
      <p class="Hero__lede">Atqui reperies, inquit, in hoc quidem pertinacem; Verum hoc idem saepe faciamus.</p>
    </div>
    <h2>A flash with colors corresponding to the safe semantic color.</h2>
    <div class="Flash">
      <div class="Flash__body--safe">
        <p class="Flash__text">Lorem Ipsum</p>
      </div>
    </div>
    <h2>A flash with colors corresponding to the caution semantic color.</h2>
    <div class="Flash">
      <div class="Flash__body--caution">
        <p class="Flash__text">Lorem Ipsum</p>
      </div>
    </div>
    <h2>A flash with colors corresponding to the danger semantic color.</h2>
    <div class="Flash">
      <div class="Flash__body--danger">
        <ul class="Flash__list">
          <li>Error One</li>
          <li>Error Two</li>
          <li>Error Three</li>
        </ul>
      </div>
    </div>
    <h2>An informational box that presents labelled content.</h2>
    <div class="InfoBox">
      <div class="InfoBox__group">
        <p class="InfoBox__label">Lorem</p>
        <p class="InfoBox__content">This is example info box content.</p>
      </div>
    </div>
    <h2>A card with an informational box</h2>
    <div class="Card">
      <div class="Card__body">
        <h2 class="Card__title">Lorem Ipsum</h2>
        <div class="InfoBox">
          <div class="InfoBox__group">
            <p class="InfoBox__label">Lorem</p>
            <p class="InfoBox__content">This is example info box content.</p>
          </div>
        </div>
      </div>
    </div>
    <h2>A button with a light background color</h2>
    <div class="u-Text--center">
      <button class="Button--solid-light">Lorem Ipsum</button>
    </div>
    <h2>A button with a dark background color</h2>
    <div class="u-Text--center">
      <button class="Button--solid-dark">Lorem Ipsum</button>
    </div>
    <h2>A button with a background color corresponding to the primary theme color</h2>
    <div class="u-Text--center">
      <button class="Button--solid-primary">Lorem Ipsum</button>
    </div>
    <h2>A button with a background color corresponding to the primary variant theme color</h2>
    <div class="u-Text--center">
      <button class="Button--solid-primary-variant">Lorem Ipsum</button>
    </div>
    <h2>A button with a background color corresponding to the secondary theme color</h2>
    <div class="u-Text--center">
      <button class="Button--solid-secondary">Lorem Ipsum</button>
    </div>
    <h2>A button with a background color corresponding to the secondary variant theme color</h2>
    <div class="u-Text--center">
      <button class="Button--solid-secondary-variant">Lorem Ipsum</button>
    </div>
    <h2>A button with a background color corresponding to the accent theme color</h2>
    <div class="u-Text--center">
      <button class="Button--solid-accent">Lorem Ipsum</button>
    </div>
    <h2>A button with a background color corresponding to the accent variant theme color</h2>
    <div class="u-Text--center">
      <button class="Button--solid-accent-variant">Lorem Ipsum</button>
    </div>
    <h2>A button with a background color corresponding to the safe semantic color</h2>
    <div class="u-Text--center">
      <button class="Button--solid-safe">Lorem Ipsum</button>
    </div>
    <h2>A button with a background color corresponding to the caution semantic color</h2>
    <div class="u-Text--center">
      <button class="Button--solid-caution">Lorem Ipsum</button>
    </div>
    <h2>A button with a background color corresponding to the danger semantic color</h2>
    <div class="u-Text--center">
      <button class="Button--solid-danger">Lorem Ipsum</button>
    </div>
    <h2>A button with a light text and border color</h2>
    <div class="u-Text--center">
      <button class="Button--outline-light">Lorem Ipsum</button>
    </div>
    <h2>A button with a dark text and border color</h2>
    <div class="u-Text--center">
      <button class="Button--outline-dark">Lorem Ipsum</button>
    </div>
    <h2>A button with a text and border color corresponding to the primary theme color</h2>
    <div class="u-Text--center">
      <button class="Button--outline-primary">Lorem Ipsum</button>
    </div>
    <h2>A button with a text and border color corresponding to the primary variant theme color</h2>
    <div class="u-Text--center">
      <button class="Button--outline-primary-variant">Lorem Ipsum</button>
    </div>
    <h2>A button with a text and border color corresponding to the secondary theme color</h2>
    <div class="u-Text--center">
      <button class="Button--outline-secondary">Lorem Ipsum</button>
    </div>
    <h2>A button with a text and border color corresponding to the secondary variant theme color</h2>
    <div class="u-Text--center">
      <button class="Button--outline-secondary-variant">Lorem Ipsum</button>
    </div>
    <h2>A button with a text and border color corresponding to the accent theme color</h2>
    <div class="u-Text--center">
      <button class="Button--outline-accent">Lorem Ipsum</button>
    </div>
    <h2>A button with a text and border color corresponding to the accent variant theme color</h2>
    <div class="u-Text--center">
      <button class="Button--outline-accent-variant">Lorem Ipsum</button>
    </div>
    <h2>A button with a text and border color corresponding to the safe semantic color</h2>
    <div class="u-Text--center">
      <button class="Button--outline-safe">Lorem Ipsum</button>
    </div>
    <h2>A button with a text and border color corresponding to the caution semantic color</h2>
    <div class="u-Text--center">
      <button class="Button--outline-caution">Lorem Ipsum</button>
    </div>
    <h2>A button with a text and border color corresponding to the danger semantic color</h2>
    <div class="u-Text--center">
      <button class="Button--outline-danger">Lorem Ipsum</button>
    </div>
    <h2>A button group with several buttons</h2>
    <div class="ButtonGroup">
      <button class="Button--solid-safe">Lorem Ipsum</button>
      <button class="Button--solid-danger">Lorem Ipsum</button>
    </div>
    <h2>A Ribbon that applies flex box spacing and positioning to child elements</h2>
    <div class="Ribbon">
      <div class="ButtonGroup">
        <button class="Button--solid-safe">Lorem Ipsum</button>
        <button class="Button--solid-danger">Lorem Ipsum</button>
      </div>
    </div>
    <h2>A small sized HR</h2>
    <hr class="u-HorizontalRule--small" />
    <h2>A medium sized HR</h2>
    <hr class="u-HorizontalRule--medium" />
    <h2>A large sized HR</h2>
    <hr class="u-HorizontalRule--large" />
    <h2>A wrapper around pagination controls to apply styles to child elements</h2>
    <div class="Paginator">
      <a href="#">Prev</a>
      <a href="#">Next</a>
      <p>Displaying records 11-20</p>
    </div>
    <h2>A form with form groups enclosing inputs</h2>
    <form class="Form">
      <div class="Form__group">
        <label>Lorem Ipsum</label>
        <input type="text" />
      </div>
      <div class="Form__group u-Element--long">
        <label>Lorem Ipsum</label>
        <input type="text" />
        <small>This is a form hint</small>
      </div>
      <div class="Form__group u-Element--medium">
        <label>Lorem Ipsum</label>
        <input type="text" />
        <small>This is a form hint</small>
      </div>
      <div class="Form__group u-Element--short">
        <label>Lorem Ipsum</label>
        <input type="text" />
        <small>This is a form hint</small>
      </div>
      <div class="Form__group">
        <label>Lorem Ipsum</label>
        <input type="text" />
      </div>
      <div class="Form__group">
        <label>Lorem Ipsum</label>
        <textarea></textarea>
      </div>
      <div class="Form__group">
        <label class="field_with_errors">Lorem Ipsum</label>
        <input class="field_with_errors" type="text" />
      </div>
      <div class="Form__action">
        <input type="submit" class="Button--solid-primary" value="Lorem Ipsum" />
      </div>
    </form>
    <h2>A form on a card with form groups enclosing inputs</h2>
    <div class="Card">
      <div class="Card__body">
        <form class="Form">
          <div class="Form__group">
            <label>Lorem Ipsum</label>
            <input type="text" />
          </div>
          <div class="Form__group u-Element--long">
            <label>Lorem Ipsum</label>
            <input type="text" />
            <small>This is a form hint</small>
          </div>
          <div class="Form__group u-Element--medium">
            <label>Lorem Ipsum</label>
            <input type="text" />
            <small>This is a form hint</small>
          </div>
          <div class="Form__group u-Element--short">
            <label>Lorem Ipsum</label>
            <input type="text" />
            <small>This is a form hint</small>
          </div>
          <div class="Form__group">
            <label>Lorem Ipsum</label>
            <textarea></textarea>
          </div>
          <div class="Form__group">
            <label class="field_with_errors">Lorem Ipsum</label>
            <input class="field_with_errors" type="text" />
          </div>
          <div class="Form__action">
            <input type="submit" class="Button--solid-primary" value="Lorem Ipsum" />
          </div>
        </form>
      </div>
    </div>
    <h2>A form with boxed form groups enclosing inputs</h2>
    <form class="Form">
      <div class="Form__group--boxed">
        <label>Lorem Ipsum</label>
        <input type="text" />
      </div>
      <div class="Form__group--boxed u-Element--long">
        <label>Lorem Ipsum</label>
        <input type="text" />
        <small>This is a form hint</small>
      </div>
      <div class="Form__group--boxed u-Element--medium">
        <label>Lorem Ipsum</label>
        <input type="text" />
        <small>This is a form hint</small>
      </div>
      <div class="Form__group--boxed u-Element--short">
        <label>Lorem Ipsum</label>
        <input type="text" />
        <small>This is a form hint</small>
      </div>
      <div class="Form__group--boxed">
        <label>Lorem Ipsum</label>
        <textarea></textarea>
      </div>
      <div class="Form__group--boxed">
        <label class="field_with_errors">Lorem Ipsum</label>
        <input class="field_with_errors" type="text" />
      </div>
      <div class="Form__action">
        <input type="submit" class="Button--solid-primary" value="Lorem Ipsum" />
      </div>
    </form>
    <h2>A form on a card with form groups enclosing inputs</h2>
    <div class="Card">
      <div class="Card__body">
        <form class="Form">
          <div class="Form__group--boxed">
            <label>Lorem Ipsum</label>
            <input type="text" />
          </div>
          <div class="Form__group--boxed u-Element--long">
            <label>Lorem Ipsum</label>
            <input type="text" />
            <small>This is a form hint</small>
          </div>
          <div class="Form__group--boxed u-Element--medium">
            <label>Lorem Ipsum</label>
            <input type="text" />
            <small>This is a form hint</small>
          </div>
          <div class="Form__group--boxed u-Element--short">
            <label>Lorem Ipsum</label>
            <input type="text" />
            <small>This is a form hint</small>
          </div>
          <div class="Form__group--boxed">
            <label>Lorem Ipsum</label>
            <textarea></textarea>
          </div>
          <div class="Form__group--boxed">
            <label class="field_with_errors">Lorem Ipsum</label>
            <input class="field_with_errors" type="text" />
          </div>
          <div class="Form__action">
            <input type="submit" class="Button--solid-primary" value="Lorem Ipsum" />
          </div>
        </form>
      </div>
    </div>
    <h2>An inline form</h2>
    <form class="InlineForm">
      <input type="text" />
      <input type="submit" class="Button--solid-dark" value="Lorem Ipsum" />
    </form>
    <h2>A link with a light text and hover color</h2>
    <div class="u-Text--center">
      <a class="Link--light" href="#">Lorem Ipsum</a>
    </div>
    <h2>A link with a dark text and hover color</h2>
    <div class="u-Text--center">
      <a class="Link--dark" href="#">Lorem Ipsum</a>
    </div>
    <h2>A link with a text and hover color corresponding to the primary theme color</h2>
    <div class="u-Text--center">
      <a class="Link--primary" href="#">Lorem Ipsum</a>
    </div>
    <h2>A link with a text and hover color corresponding to the primary variant theme color</h2>
    <div class="u-Text--center">
      <a class="Link--primary-variant" href="#">Lorem Ipsum</a>
    </div>
    <h2>A link with a text and hover color corresponding to the secondary theme color</h2>
    <div class="u-Text--center">
      <a class="Link--secondary" href="#">Lorem Ipsum</a>
    </div>
    <h2>A link with a text and hover color corresponding to the secondary variant theme color</h2>
    <div class="u-Text--center">
      <a class="Link--secondary-variant" href="#">Lorem Ipsum</a>
    </div>
    <h2>A link with a text and hover color corresponding to the accent theme color</h2>
    <div class="u-Text--center">
      <a class="Link--accent" href="#">Lorem Ipsum</a>
    </div>
    <h2>A link with a text and hover color corresponding to the accent variant theme color</h2>
    <div class="u-Text--center">
      <a class="Link--accent-variant" href="#">Lorem Ipsum</a>
    </div>
    <h2>A link with a text and hover color corresponding to the safe semantic color</h2>
    <div class="u-Text--center">
      <a class="Link--safe" href="#">Lorem Ipsum</a>
    </div>
    <h2>A link with a text and hover color corresponding to the caution semantic color</h2>
    <div class="u-Text--center">
      <a class="Link--caution" href="#">Lorem Ipsum</a>
    </div>
    <h2>A link with a text and hover color corresponding to the danger semantic color</h2>
    <div class="u-Text--center">
      <a class="Link--danger" href="#">Lorem Ipsum</a>
    </div>
    <h2>A box link with a light text and border color</h2>
    <div class="u-Text--center">
      <a class="BoxLink--light" href="#">Lorem Ipsum</a>
    </div>
    <h2>A box link with a dark text and border color</h2>
    <div class="u-Text--center">
      <a class="BoxLink--dark" href="#">Lorem Ipsum</a>
    </div>
    <h2>A box link with a text and border color corresponding to the primary theme color</h2>
    <div class="u-Text--center">
      <a class="BoxLink--primary" href="#">Lorem Ipsum</a>
    </div>
    <h2>A box link with a text and border color corresponding to the primary variant theme color</h2>
    <div class="u-Text--center">
      <a class="BoxLink--primary-variant" href="#">Lorem Ipsum</a>
    </div>
    <h2>A box link with a text and border color corresponding to the secondary theme color</h2>
    <div class="u-Text--center">
      <a class="BoxLink--secondary" href="#">Lorem Ipsum</a>
    </div>
    <h2>A box link with a text and border color corresponding to the secondary variant theme color</h2>
    <div class="u-Text--center">
      <a class="BoxLink--secondary-variant" href="#">Lorem Ipsum</a>
    </div>
    <h2>A box link with a text and border color corresponding to the accent theme color</h2>
    <div class="u-Text--center">
      <a class="BoxLink--accent" href="#">Lorem Ipsum</a>
    </div>
    <h2>A box link with a text and border color corresponding to the accent variant theme color</h2>
    <div class="u-Text--center">
      <a class="BoxLink--accent-variant" href="#">Lorem Ipsum</a>
    </div>
    <h2>A box link with a text and border color corresponding to the safe semantic color</h2>
    <div class="u-Text--center">
      <a class="BoxLink--safe" href="#">Lorem Ipsum</a>
    </div>
    <h2>A box link with a text and border color corresponding to the caution semantic color</h2>
    <div class="u-Text--center">
      <a class="BoxLink--caution" href="#">Lorem Ipsum</a>
    </div>
    <h2>A box link with a text and border color corresponding to the danger semantic color</h2>
    <div class="u-Text--center">
      <a class="BoxLink--danger" href="#">Lorem Ipsum</a>
    </div>
  </body>
</html>
```
