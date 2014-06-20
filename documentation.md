# Documentation


## Badge
--------
The `badge` block is used to highlight small pieces of content.

code: 

``` html
<span class="badge">1</span>
```

preview:

<span class="badge">1</span>

## Box
------
The  `box`  block simply boxes off content.

code: 

``` html
<div class="box xs-p1">
    <h1 class="xs-mb1">Some Content</h1>
    <p>
        Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
        Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
        Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
        Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
    </p>
</div>
```

preview:

<div class="box xs-p1">
    <h1 class="xs-mb1">Some Content</h1>
    <p>
        Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
        Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
        Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
        Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
    </p>
</div>

## Button
---------
`button` object is used to provide consistant styles across all types of button elements.

`button--block` modifier makes the button block span the width of the container.


code:

``` html
<a href="#" class="button xs-prl1">Click Here</a>
<a href="#" class="button button--block">Click Here</a>
```

preview:

<a href="#" class="button xs-prl1">Click Here</a>
<a href="#" class="button button--block">Click Here</a>


## Container
------------
`container` element wraps your content and sizes it according to your breakpoint settings.

`fluid-container` class works like container but with no breakpoints, resizing constantly.

`container--fixed-top` modifier fixes your container to the top of the screen.

code: 

``` html
<div class="container">
	I am the page's content, centered within the viewport, resizing at breakpoints.
</div>
<div class="container-fluid">
	I am the page's content, centered within the viewport, resizing constantly (no breakpoints).
</div>
```


## Field
--------
The `field` block is used to wrap inputs into. You can also wrap specific states to a field like, if its invalid/valid/required/etc.
That would look something like `field--is-invalid`.

code:

``` html
<div class="field">
	<input type="text" class="input input--text" value="Hello World">
	<div class="field__message">Message Content</div>
</div>
```

preview:

<div class="field">
	<input type="text" class="input input--text" value="Hello World">
	<div class="field__message">Message Content</div>
</div>

## Flashbar
-----------
The `flashbar` block is used to display flash messages.

code:

``` html
<div class="flashbar">
	<div class="container">
		<div class="layout xs-prlh0">
			<div class="layout__item">Hello World</div>
		</div>
	</div>
	<div class="flashbar__close">×</div>
</div>
```

preview:

<div class="flashbar">
	<div class="container">
		<div class="layout xs-prlh0">
			<div class="layout__item">Hello World</div>
		</div>
	</div>
	<div class="flashbar__close">×</div>
</div>

## Navigationbar
----------------
The `navigationbar` block is used for navigation of the site.

code:

``` html
<div class="navigationbar">
	<div class="container--fluid">
		<div class="navigationbar__header">
			<a class="navigationbar__header__logo" href="#">Hello</a>
			<a class="navigationbar__header__toggle">
				<img alt="Toggle Menu" class="icon icon--menu" height="16" src="images/ecd9f4dd.spacer.gif" width="20">
			</a>
		</div>
		<nav class="collapse navigationbar__collapse">
			<ul class="navigation navigationbar__navigation navigationbar__navigation--right">
				<li class="navigation__item">
					<a class="navigation__link navigation__link--world" href="#">World</a>
				</li>
			</ul>
		</nav>
	</div>
</div>
```

preview:

<div class="navigationbar">
	<div class="container--fluid">
		<div class="navigationbar__header">
			<a class="navigationbar__header__logo" href="#">Hello</a>
			<a class="navigationbar__header__toggle">
				<img alt="Toggle Menu" class="icon icon--menu" height="16" src="images/ecd9f4dd.spacer.gif" width="20">
			</a>
		</div>
		<nav class="collapse navigationbar__collapse">
			<ul class="navigation navigationbar__navigation navigationbar__navigation--right">
				<li class="navigation__item">
					<a class="navigation__link navigation__link--world" href="#">World</a>
				</li>
			</ul>
		</nav>
	</div>
</div>

## Tabbed Navigation
-------
The `tabbed-navigation` block is used to build a navigation that has equal width navigation items.

code:

``` html
<ul class="tabbed-navigation">
	<li class="tabbed-navigation__item">
		<a href="#">Item 1</a>
	</li>
	<li class="tabbed-navigation__item tabbed-navigation__item--is-active">
		<a href="#">Item 2</a>
	</li>
	<li class="tabbed-navigation__item">
		<a href="#">Item 3</a>
	</li>
</ul>
```

preview:

<ul class="tabbed-navigation">
	<li class="tabbed-navigation__item">
		<a href="#">Item 1</a>
	</li>
	<li class="tabbed-navigation__item tabbed-navigation__item--is-active">
		<a href="#">Item 2</a>
	</li>
	<li class="tabbed-navigation__item">
		<a href="#">Item 3</a>
	</li>
</ul>
