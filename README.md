# tat-css
Minimalistic flexbox CSS framework

Objectives
----------

CSS flexbox is already at around 98% browser support by usage. Thus, it is time to put an end to floats and inline-blocks and start creating beautiful responsive web sites using flexbox. If you prefer a minimalistic and non-opinionated CSS framework in the spirit of PURE CSS, you can give TAT a try. 

This frameworks aims to:
- be very lightweight
- provide only the most common usages of flexbox and leave all the rest to your projects stylesheets
- deal only with layouts. No design-related stuff at all.
- skip flexbox options that still have low support

Please have in mind that TAT is still in development. Until version 1.0 the naming of some elements might change. 

Get Started
-----------

There is only one file you need to include: tat.min.css
Doing a CSS reset/normalise is up to you and is not included.

**Naming logic**

TAT aims to be very logical and simple in its class namings. Every class starts with "tat-", followed by row, alignment or element prefix, than by media query prefix and finally by sizing parameters.

**Container types**

There are 4 container types in TAT.CSS: 
- single row (tat-r)
- single column (tat-c)
- multiple rows grid (tat-g)
- multiple columns (newspaper-style) grid (tat-n).

Every grid can be reversed in order by adding the "-r" parameter, i.e. "tat-c-r" is a reversed single column.

**Grid alignments**

The horizontal alignment options are: tat-center, tat-left, tat-right, tat-hspace, tat-heven

The vertical alignments are: tat-top, tat-middle, tat-bottom, tat-vspace

**Media queries**

TAT uses the same media queries as PURE CSS and follows the "mobile first" order. 

- sm is above 35.5em
- md is above 48em
- lg is above 64em
- xl is above 80em

Example:
class="tat-c tat-r-md" will produce a column order of elements in resolutions up to 48em and a row order above that.

**Flex units**

The "flex" unit in flexbox is very powerful and has plenty of use-cases in responsive web design. TAT only features a few predefined flex units fromthe endless possibilities – the ones that will probably be used most often in your project.

- tat-f-0-1 - element will not grow, but will shrink if needed
- tat-f-1-0 - element will grow to fill up space but will not shrink below its predefined width
- tat-f-0-0 - element is fixed size and will neither grow, nor shrink
- tat-f-1-1 - element will fully adapt its size to what is available
- tat-f-0 to tat-f-11 - these concern only element growing above its predefined size. Keep in mind these numbers are proportions, so tat-f-2 will grow twice as much as tat-f-1 if they are in the same row.
- tat-f--0 to tat-f--11 - same as above, but concern element shrinking.

Flex units have no media queries in TAT. The idea behind flex units is to be natively adaptive. If you want to change proportions use the standard units.

**Fixed units**

The fixed units have a fixed width that is constant. You can use them in a tat-g grid, or you can combine them with flex rules in single rows/columns.

The units are proportion based and are named very similarly to PURE CSS, starting from tat-u-1 to tat-u-23-24. A major difference from Pure CSS is that in TAT there are no repeating proportions, so since there is tat-u-1-2 there is no tat-u-12-24. 

The media query parameter goes after the "u" parameter: tat-u-sm-1-2, tat-u-lg-1-4, etc.

**Other specifics**

The beauty of flexbox is that every unit can also be a container, so this is quite possible: class="tat-u-1-2 tat-r". And it will clean up your html big time!

You can change the order of elements, no only be reversing the whole container, but individually. Since this has a more case-specific usage it is not part of the framework - you will have to do it in your site stylesheet.

You can also change the alignment of single elements in the container. I.e. all are aligned to the top, but one is aligned to the bottom. This is in the roadmap to be featured in TAT.

Examples
--------

You probably start building a website from its header. Designing the header with CSS used to be a pain - the logo has to stay the same size, the slogan needs to adjust to available space and the menu changes its design completely from mobile to desktop. One would resort to a complicated combination of floats, absolute positioning, etc. Not anymore! With flexbox its so much easier. Here is the most basic example:

```html
<header class="tat-c tat-r-md tat-middle">
  <div id="logo" class="tat-f-0-0">Logo</div>
  <div id="slogan" class="tat-f-1-1">Your company slogan!</div>  
</header>
```

The logo div will remain the size of the image file (or the size set to #logo in your stylesheet), while the slogan div will fill in the remaining space and if the text longer it will break into multiple text rows, while the two divs are always middle-aligned (center-aligned column on mobile).
