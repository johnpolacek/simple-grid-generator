# Simple Grid Generator (SASS)

A SASS grid generator for creating responsive grids with some nice features. View an example at [johnpolacek.github.io/simple-grid](http://johnpolacek.github.io/simple-grid/).

## Features


#### Easy to Use
```
@import 'grid.generator.scss';
@include gridGenerator();
```

#### Set Your Columns
Switch to a 18-column or 24-column grid instead.

```
@include gridGenerator(18);
```

#### Breakpoints and Breakpoint Prefixes
Change the breakpoints, or add in more. Name the prefixes whatever you like xs-, xl-, etc. If you prefer, set ems for your breakpoints.

```
@include gridGenerator(
    12,
    (0, 20em, 30em, 60em, 80em),
    (xs-,s-,m-,l-,xl-),
    'em'
);
```

Breakpoint prefixing allows for markup that sets a default grid width, then overrides at different screen widths.

```
<div class="grid-3 m-grid-6 s-grid-12">
<!-- 
	In a 12-column grid, this translates to: 
		- Quarter width by default
		- Half width at the medium breakpoint
		- Full width at the small breakpoint
-->
```


#### Spacing Helpers
For quick, easy layouts, set custom utility classes to set consistent padding and margin on all your elements.

```
@include gridGenerator(
    12,
    (0, 480px, 800px),
    (s-,m-,l-),
    'px',
    $spaceUnits: (.5em,1em,2em)
);
```
In your HTML:

```
<div class="pad-2 m-pad-1 s-pad-0">
<div class="pad-bottom-4 marg-bottom-2">
<div class="pad-vertical-1 pad-sides-2">
```

You can use responsive breakpoint prefixing on these as well.

```
<div class="pad-sides-2 s-pad-sides-1">
```

Or don’t use any spacing helpers, if you prefer.

```
@include gridGenerator(
    12,
    (0, 480px, 800px),
    (s-,m-,l-),
    'px',
    $spaceUnits: false
);
```



## License
Author & copyright (c) 2015: [John Polacek](http://johnpolacek.com), Dual MIT & GPL license
