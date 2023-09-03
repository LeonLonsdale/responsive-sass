# Sass Mixins for Responsive Design

A collection of useful mixins for responsive web development.

## Introduction

This collection of mixins should be installed as a partial to your main sass structure. I personally keep this in my `abstracts` directory.

The collection consists of:

- Media Query
- Property clamp insertion
- Inline clamp insertion

## Installation

Simply put \_responsive.scss in your abstracts folder and remember to `@forward` it in any \_index.scss.

## How to use it

### Media Queries

Within the file you'll find a number of sass variables:

```
$xs: 375;
$sm: 480;
$md: 768;
$lg: 1024;
$xl: 1200;
$xxl: 1201;
```

You can change these to any custom set you'd prefer. However, the use of the mixin is not limited to this preset anyway and allows custom viewport entry.

To call the mixin:

`@include <x>.breakpoint(y,z);`

- replace <x> with your namespace.
- y can be replaced with any of the variable names above (excluding the $)
- z can be replaced with min, max, or range.

Input:

![alt text](/img/resp-ex-1-pre.png)

Output:

![alt text](/img/resp-ex-1.png)

Input:

![alt text](/img/resp-ex-2-pre.png)

Output:

![alt text](/img/resp-ex-2.png)

Input:

![alt text](/img/resp-ex-3-pre.png)

Output:

![alt text](/img/resp-ex-3.png)

### Property clamp insertion

This inserts both the property and the clamp.

Usage:

`@include <x>.getclamp(property,minsize,maxsize,minviewport,maxviewport);`

For example:

Input:

![alt text](/img/resp-ex-4-pre.png)

Outcome:

![alt text](/img/resp-ex-4.png)

## Inline Clamp

Inserts the clamp without the property. Useful for global variables.

Useage:

`@include <x>.insertClamp(minsize,maxsize,minviewport,maxviewport)`

For example:

Input:

![alt text](/img/resp-ex-5-pre.png)

Output:

![alt text](/img/resp-ex-5.png)

### Custom Values

In all examples above, the built-in Sass variables are used. You can replace these values by simply passing in a custom number into the mixin call. This allows you to still use the mixins for rare one off occurances whilst maintaining your set variables.

When doing this, enter them in pixel format but omit 'px'. So 800px would be entered as 800. For media queries, this will be converted to em, and for clamps it will be converted to rem.

## Important to note

In all cases, the mixins assume that 1rem is 10px - to achieve this, in your html / root, set your font-size to 62.5%. You can then reset the font size in your body to 1.6rem.
