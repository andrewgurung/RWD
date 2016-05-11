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
