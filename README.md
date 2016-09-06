# Micro
## A simple CSS grid system.

```sass
@import "micro";
@include micro(12, 5px);
```

Micro is more of a grid system builder than a grid system itself. Specify the number of columns you need and the gutter between each and Micro spits out a series of classes and Sass placeholders.

### Classless

```sass
@import "micro";
@include micro(12, 5px, false);
```

Don’t want classes? You like your stylesheet clean? The third parameter allows you to turn off the classes and have just Sass placeholders.

### Prefixes

Need to use two different grid systems on a single site? You might have good reasons.

```sass
@import "micro";
@include micro(12, 5px, false, "ms-");
```

The fourth parameter allows you to prefix the classes and Sass placeholders.

### Classes & Sass Placeholders

Micro generates two sets of classes and Sass placeholders: columns and column-offset.

```html
<div class="container row">
	<nav class="columns-4 column-offset-1"></nav>
	<main class="columns-7"></main>
</div>
```

But if you like your HTML to be more semantic or you like to only include CSS that you will use, use placeholders and turn off the classes.

```sass
@import "micro";
@include micro(12, 5px, false);

.container {
	@extend %row;
}
nav {
	@extend %columns-4;
	@extend %column-offset-1;
}
main {
	@extend %columns-8;
}
```

```html
<div class="container">
	<nav></nav>
	<main></main>
</div>
```

That HTML is much more clean.