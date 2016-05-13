## SVG (scalable vector graphics)

### Inserting SVGs into your web pages

1. Using an img tag
  ```html
  <img src="svgfile.svg" alt="Amazing line art of a scone" />
  ```

2. Using an object tag
  - Recommended by the W3C for holding non-HTML content
  - Is accessible with JavaScript
  - Fallback mechanism (Can include text or image)
  ```html
  <object data="svgfile.svg" type="image/svg+xml">
   <span class="fallback-info">Your browser doesn't support SVG</span>
  </object>
  ```

3. Insert an SVG as a background image
  ```css
  background-image: url('image.svg');
  ```
