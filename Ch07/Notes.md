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

4. Inserting an SVG inline
- As SVG is merely an XML document, you can insert it directly into the HTML.

  ```html
  <div>
   <h3>Inserted 'inline':</h3>
     <span class="inlineSVG">
       <svg id="svgInline" width="198" height="188" viewBox="0 0 198 188" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
         <title>Star 1</title>
           <g class="star_Wrapper" fill="none" fill-rule="evenodd">
             <path id="star_Path" stroke="#979797" strokewidth="3" fill="#F8E81C" d="M99 154l-58.78 30.902 11.227-65.45L3.89473.097l65.717-9.55L99 4l29.39 59.55 65.7169.548-47.553 46.353 11.22665.452z" />
           </g>
       </svg>
     </span>
  </div>
  ```
