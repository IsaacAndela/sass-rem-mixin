# SASS Rem Mixin

SASS Rem Mixin aims to make using [rem](http://dev.w3.org/csswg/css-values/#rem) values with pixel fallbacks easy in [SASS](http://sass-lang.com/).


## Including

Save `_rem.scss` in you sass folder. And include it like so:

	// $rem represents the fontsize of the root element in pixels
	// and will be used to convert rem values to pixel values.
	// It should be specified unitless and is optional.
	// The default value is 10.
	// If you wish to override the default $rem value
	// you should do so before importing the rem partial.
	// E.g. a $rem of 10 will result in:
	// html { font-size: 10px; }
	$rem: 10;

	// Import _rem.scss from the path where you saved it in your project.
	@import "path/to/rem";


## Usage

### `@include rem($propName, $propValue)`

- `$propName` is the name of the property you wish to apply the values to, e.g. *margin*.

- `$propValue` is the property value you wish to use with rems. Any rem values and unitless values are converted to rems. Other values are left alone.

#### Examples

This:

	section {
		@include rem(margin, 2rem 10% 2rem 2em);
	}

Will convert to:

	section {
		margin: 20px 10% 5rem 20px;
		margin: 2rem 10% 2rem 2em;
	}

And this:

	a {
		@include rem(font-size, 1.6);
	}

Will convert to:

	a {
		font-size: 16px;
		font-size: 1.6rem;
	}