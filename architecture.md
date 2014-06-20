# Architecture

## Overview
---

* Settings **[1]**
* Tools
* Generic
* Base
* Blocks
* Extensions
* Trumps

<br />

1. Settings are only used if you're using a preprocessor.


## Good CSS is good
---

First, lets talk about writing good CSS.

1. Write descriptive comments for you and your team.
2. Use [BEM Syntax](http://csswizardry.com/2013/01/mindbemding-getting-your-head-round-bem-syntax/).
3. Use exactly 1 space after each selector.
4. Sort your properties alphabetically. (this allows you to easily scan through your code because your mind knows how to read things quicker if they're indexed. This is why libraries have them ) **[1]**
5. if you're using a preprocessor like Scss put your extends before your mixins and both of them at the top of the selector. If you think about it this is a logical thing to do and will save you from headaches down the road. if you use extend you want those properties to come first, then you will mixin functionality using a mixin, and finally you will describe that selector using the properties you set.


``` scss
/*------------------------------------*\
#MEDIA
\*------------------------------------*/

/**
 * Place any image- and text-like content side-by-side, as per:
 * stubbornella.org/content/2010/06/25/the-media-object-saves-hundreds-of-lines-of-code
 */

.media {
   /**
    *
    * 1. clear the float for the element.
    * 2. force the element display to block.
    *
    */

    @include clearfix;    /* [1] */
    display: block;       /* [2] */

    &__object {

       /**
        *
        * 1. float element to the left.
        * 2. add some spacing for the `.media__body` content
        *    to breath.
        *
        */

        float: left;        /* [1] */
        margin-right: 1rem; /* [2] */

        > img {
           /**
            *
            * 1. set element to block to remove character
            *    spacing from inline-block elements.
            *
            */
            display: block;   /* [1] */
        }
    }

    &__body {
       /**
        *
        * 1. force display to block.
        * 2. set element to overflow so content
        *    doesn't wrap around `.media__object`.
        *
        */
        display: block;     /* [1] */
        overflow: hidden;   /* [2] */

        &,
        > :last-child {
           /**
            *
            * 1. remove `margin: bottom;` so sibiling `.media`
            *    objects can sit flush together.
            *
            */
            margin-bottom: 0; /* [1] */
        }
    }
}
```


1. Only sort properties alphabetically if you can, for some reason someone decided to make the border-radius properties the only properties that can't be sorted alphabetically because of how the CSS Cascade works. Example below.


``` scss
border-radius: 10px;
border-top-left-radius: 5px;
```

``` scss
/* instead they should of named them like this, but oh well.... */
border-radius: 10px;
border-radius-top-left: 5px;
```

## Feature Dectection
---
*Very often do I see this approach, its not bad, but it doesn't make much sense to me.*

For example, if you were building a responsive site then you'd obviously be coding for something that is mobile at some point.

And usually a designer will want to make buttons/inputs bigger so they're more friendly to mobile users, which they should be doing!

However, you as the web developer will often do something like this:

``` scss
.button {
    ...
    height: 3em;
}

.input {
    ...
    height: 3em;
}

@media (min-width: 768px) {
    // bigger than mobile.
    .button {
        height: 1em;
    }

    .input {
        height: 1em;
    }
}
```

This to me, is a big no no. and that is why we should be using feature css.

## Feature CSS
---

Ever heard of the amazing [Modernizr.js](http://modernizr.com/)?

Well, if not. its a library that will add classes to your HTML element for features that are available to the browser of the current user.

You can write your own tests too so if you need to test a feature that isn't apart of Modernizr then you can add it! just make sure to read the docs first.

So, using something like Modernizr the previous solution would look like this.

``` scss
.button {
    ...
    height: 1em;

    .touch & {
        height: 3em;
    }
}

.input {
    ...
    height: 1em;

    .touch & {
        height: 3em;
    }
}

```

**This is much better.**

1. the code is not using a media query.
2. the code is only going to be run on a device that is a touch enabled device.
3. less lines of code!


## Settings
---

settings is a place where you put all of your configuration, the things that setup your site. Like how many rows are in your grid, or the names of your color variables in your site, maybe sprite variables if you're using Compass, or if you're using some third party framework like Fortitude.


the folder structure might look something like this:

```
settings
├─── _defaults.scss
├─── _colors.scss
├─── _sprites.scss
└─── _fortitude.scss
```

## Tools
---

this is a folder where you put all of your tools! (functions, mixins).

1. functions
2. mixins

Example folder structure:

```
tools
├─── _functions.scss
└─── _mixins.scss
```


## Generic
---

This is a folder for sitewide styles that should "clean" your elements from user agent styles. AKA Default browser Styles.

1. box sizing styles (if you don't support IE7 or lower)
2. normalize.css (for normalizing the browsers defaults)
3. generic shared styles of elements (for things like margin/padding on specific elements)
4. reset styles (if you want to reset specific elements like the margin on a body element)

Example folder structure:

```
generic
├─── _box-sizing.scss
├─── _normalize.scss
├─── _reset.scss
└─── _shared.scss
```

## Base
---

this is a folder where you should put all of the common/global page styles for your site, things like setting up which font your site uses globally, setting up the font-sizes/line-heights on elements, tools like a clearfix.

1. page styles.
2. paragraph styles.
3. heading styles.
4. list styles.
5. image styles.
6. clearfix

Example folder structure:

```
base
├─── _clearfix.scss
├─── _headings.scss
├─── _images.scss
├─── _lists.scss
├─── _page.scss
└─── _paragraphs.scss
```

## Blocks
---

this is a folder where you put all of the blocks (reusable chunks of code). [1]


1. Generally you should not give these initial implementations theme styles, purely just styles that represent the structure of the block.

<br />

Example folder structure:

```
blocks
├─── _bare-list.scss
├─── _block-list.scss
├─── _box.scss
├─── _buttons.scss
├─── _flag.scss
├─── _inputs.scss
├─── _layout.scss
├─── _media.scss
├─── _ui-list.scss
└─── _tabs.scss
```

## Extensions
---

this is a folder where you put all of the code that wraps blocks together. [1]

1. This is the area where you should give something a visual theme/style.


1. button variations (extend from buttons)
2. form related styles (extend from inputs)
3. panel component (extend from box)
4. dropdowns (extend from lists)
5. etc

Example folder structure:

```
extensions
├─── _forms.scss
├─── _buttons.scss
├─── _dropdowns.scss
├─── _navigations.scss
└─── _navigationbars.scss
```

I will go into more detail of all of these later. its now 12:13AM.

Goodnight!

## Trumps
---

This is a place where you should put all of your CSS that you want to always **trump** other CSS.
Maybe you have a grid system, and that grid system has helpers that should always win over any other `class`
Well, rather than throwing `!important` on every property you should put it in the trumps folder and include everything in your trumps folder last in your Scss file.

Example folder structure:

```
trumps
├─── _responsive-font.scss
├─── _responsive-width.scss
├─── _responsive-visiblity.scss
├─── _responsive-height.scss
└─── _responsive-box-model.scss
```
