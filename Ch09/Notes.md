## Forms with HTML5 and CSS3

### Component parts of HTML5 Forms

1. fieldset
  - Group related elements in a form.
  Surrounds everything in a container UI
  ```html
  <fieldset>
    <legend>Information</legend>
    Name: <input type="text"><br>
    Email: <input type="text"><br>
    Date of birth: <input type="text">
  </fieldset>
  ```

2. legend
  - Display name of the `fieldset` container

3. placeholder
  - Attribute displayed by default until field gains focus
  ```html
  <input id="film" name="film" type="text" placeholder="e.g. King Kong" required>
  ```

  ```css
  input:placeholder-shown {
    color: #333;
  }
  ```

4. required
  - Throws a warning message (specific to browser in terms of content and styling) if form is submitted without the field

5. autofocus
  ```html
  <input id="search" name="search" type="search" placeholder="Wyatt Earp" autofocus>
  ```

6. autocomplete
  ```html
  <input id="tel" name="tel" type="tel" placeholder="1-234-546758" autocomplete="off" required>

  <!-- Or set auto complete off in the entire form -->
  <form id="redemption" method="post" autocomplete="off">
  ```

7. list and datalist
  - Autosuggests values when user types in something
  - But user can enter any text
  ```html
  <input id="awardWon" name="awardWon" type="text" list="awards">
  <datalist id="awards">
    <select>
      <option value="Best Picture"></option>
      <option value="Best Director"></option>
      <option value="Best Adapted Screenplay"></option>
      <option value="Best Original Screenplay"></option>
    </select>
  </datalist>
  ```

## HTML5 input types

1. email [type="email"]
  - Supporting browsers expect a user input that matches the syntax of an e-mail
  ```html
  <input type="email" placeholder="john.doe@gmail.com" required>
  ```

2. number [type="number"]
  - Displays spinner controls (click up or down to alter the value input)
  - `min` and `max` ranges can be set
  - `step` is the interval at which the number is changed
  ```html
  <input type="number" min="1929" max="2015" step="10" required>
  ```

3. url [type="url"]
    ```html
    <input id="web" name="web" type="url" placeholder="www.mysite.com">
    ```

4. tel [type="tel"]
  - Expect telephone number
  ```html
  <input id="tel" name="tel" type="tel" placeholder="1-234-546758" autocomplete="off" required>
  ```

5. search [type="search"]
  - works like a standard text input
  ```html
  <input id="search" name="search" type="search" placeholder= "Wyatt Earp">
  ```

6. pattern [pattern=""]
  ```html
  <input id="name" name="name" pattern="([a-zA-Z]{3,30}\s*)+[a-zA- Z]{3,30}" placeholder="Dwight Schultz" required>
  ```

7. color [type="color"]
  - color picker in supporting browsers
  ```html
  <input id="color" name="color" type="color">
  ```

8. date [type="date"]
  - Chrome and Opera supports calendar
  ```html
  <input id="date" type="date" name="date">
  ```

9. month [type="month"]
  ```html
  <input id="month" type="month" name="month">
  ```

10. week [type="week"]
  ```html
  <input id="week" type="week" name="week">
  ```

11. time [type="time"]
  - 24 hr format
  ```html
  <input id="time" type="time" name="time">
  ```

12. range [type="range"]
  - Code snippet to display selected value in real time as you move the slider interface
  ```html
  <input id="howYouRateIt" name="howYouRateIt" type="range" min="1" max="10" value="5" onchange="showValue(this.value)"><span id="range">5</span>
  ```

  ```js
  function showValue(newValue) {
    document.getElementById("range").innerHTML=newValue;
  }
  ```

### Polyfill non-supporting browsers
- Download Webshims lib (http://github.com/aFarkas/webshim/downloads)
```html
<script src="js/jquery-2.1.3.min.js"></script>
<script src="js-webshim/minified/polyfiller.js"></script>
<script>
//request the features you need:
webshim.polyfill('forms');
</script>
```  

### Highlight label with asterisk if error
- With this selector, when the item is hovered over, styles are applied to item general-sibling if it is at the same DOM level as item and follows it.
  `.item:hover ~ .item-general-sibling {}`

- Here, when the item is hovered over, styles are applied to item-adjacent-sibling if it is the adjacent sibling element of item (straight after it in the DOM).
  `.item:hover + .item-adjacent-sibling {}`
Example:
```html
<label for="film">The film in question?</label>
<input id="film" name="film" type="text" placeholder="e.g. King Kong" required/>
```

Problem:
- CSS selector can only select adjacent sibling straight after it in the DOM.

Solution:
- Write `input` tag before `label`
- Use `Flexbox's` row-reverse or column-reverse to display the label before the input
- But internally the underlying DOM would still have label after input. So we can use CSS selector to select the label

Code Snippet:
```html
<input id="film" name="film" type="text" placeholder="e.g. King
Kong" required/>
<label for="film">The film in question?</label>
```

```css
input:required + label:after {
content: "*";
font-size: 2.1em;
position: relative;
top: 6px;
display: inline-flex;
margin-left: .2ch;
transition: color, 1s;
}

input:required:invalid + label:after {
color: red;
}
input:required:valid + label:after {
color: green;
}
```
