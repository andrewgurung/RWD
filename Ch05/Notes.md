## Quick and useful CSS tricks

### CSS multi-column layouts
- Breaks long texts into columns
```html
<main>
 <p>lloremipsimLoremipsum dolor sit amet, consectetur
<!-- LOTS MORE TEXT -->
</p>
</main>
```

1. Fixed column width: Display long texts into multiple columns with 12em width
  ```css
  main {
   column-width: 12em;
   column-gap: 2em; /* Adds gap */
   column-rule: thin dotted #999; /* Adds column divider */
  }
  ```

2. Column count
  ```css
  main {
   column-count: 4; /* Limits the column count to 4 */
  }
  ```

### Word Wrap
- Wraps a long text by breaking into multiple lines
```html
<main>
  <a href="#">http://dowebsitesneedtolookexactlythesameineverybrowser.com/</a>
</main>
```

```css
main {
	word-wrap: break-word;
}
```

### Text ellipsis
- Add `...` for longer text if it goes beyond a given width

```html
<p class="truncate">OK, listen up, I've figured out the key eternal
happiness. All you need to do is eat lots of scones.</p>
```

```css
.truncate {
 width: 520px;
 text-overflow: ellipsis;
 white-space: no-wrap;
}
```

## Feature forks in CSS
- If/else condition where if a browser supports a feature display a certain chunk of code, if not display something else.

Two possible approaches:

1. Purely based on CSS: Fewer browser implementations
2. JavaScript library: Broader support

### Feature queries
- Native solution to forking code in CSS
- Similar in syntax to `media queries`

```css
@supports (display: flex  and (pointer: coarse)  or (transform: translate3d(0, 0, 0)) {
  .Item {
    display: inline-flex;
  }
}

@supports not (display: flex) {
  .Item {
    display: inline-block;
  }
}
```

### Modernizr
- Until `@supports` is more widely supported, we can use `Modernizr`
https://modernizr.com/

1. Modernizr JavaScript support
```js
$(document).ready(function()
{
  if (Modernizr.websockets)
  {
    $("#result").html('Your browser has support for Web Sockets');
  }
  else
  {
    $("#result").html('Your browser does not support Web Sockets');
  }
});
```

2. Modernizr CSS support

```css
div.wsno, div.wsyes { display: none }
.no-websockets div.wsno { display: block }
.websockets div.wsyes { display: block }
```

```html
<div class="wsno">
  Your browser does not support WebSockets.
</div>

<div class="wsyes">
  Your browser supports WebSockets.
</div>
```
--------------

## New CSS3 selectors

### Attribute selector

```css
img[alt] { /* All images with alt attribute*/
  border: 3px dashed #e15f5f;
}
```

1. 'beginning with' substring matching attribute selector
  Eg: img[alt^="film"]
2. 'contains an instance of' substring matching attribute selector
  Eg: img[alt*="film"]
3. 'ending with' substring matching attribute selector
  Eg: img[alt$="film"]

------------

## CSS3 structural pseudo-classes
```css
/* Introduced in CSS 2.1 */
div:first-child {
}

/* Introduced in CSS 3 */
div:last-child {
}

/* Select all odd links */
div:nth-child(odd) {  
}

/* Select all even links*/
div:nth-child(even) {  
}


/* Select any (n) parameter */
div:nth-child(3) {  
}

/* Select from a specific type/class whichever is selected first
<span class="vehicle"></span>
<span class="vehicle"></span>   ==> Selected
<span class="vehicle"></span>
<span class="vehicle"></span>   ==> Selected
<div class="vehicle"></span>
<div class="vehicle"></span>
<div class="vehicle"></span>
<div class="vehicle"></span>
*/
.vehicle:nth-of-type(2n) {
  /* Div types aren't selected in this example */
}

/* Select from a specific type/class */
.vehicle:nth-last-of-type(2n) {
}

/* negation selector */
:not(p) {
}

/* Select if an element is empty
<div class="vehicle"></div>
*/
.vehicle {
  background-color: indigo;
}
.vehicle:empty{
  display:none
}
```

## CSS custom properties and variables

```css
/*  :root pseudo-class always references the top-most parent element in a document structure */
:root {
 --MainFont: 'Helvetica Neue', Helvetica, Arial, sans-serif;
}
```

Reference later using `var()`

```css
.Title {
 font-family: var(--MainFont);
}
```
