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

3. 
