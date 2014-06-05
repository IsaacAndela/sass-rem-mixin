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


## The MIT License (MIT)

Copyright (c) 2014 Isaac Andela

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.