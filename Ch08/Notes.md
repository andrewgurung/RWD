## Transitions, Transformations, and Animations

CSS can handle majority of motion jobs with 3 principal agents:
1. Transitions
2. Transformations
3. Animations

### Transitions
-  Display visual 'effect' between one state and another
- Apply transition declaration on the 'from' state
- Four properties:
  1. transition-property (`all` to transition every property)
  2. transition-duration
  3. transition-timing-function (Eg: ease, linear, ease-in, ease-out, etc)
  4. transition-delay

```css
/* From State */
a {
  transition: box-shadow 1s ease 0s;
}

/* To State */
a:hover {
  box-shadow: inset 0 -3px 0 #CC3232;
}

/*  multiple properties transition*/
.style {
 /* ...(more styles)... */
 transition-property: border, color, text-shadow;
 transition-duration: 2s, 3s, 8s;
}
```

### Transform
```css
/* Enlarge elements */
transform: scale(1.4);

/* Shrink elements */
transform: scale(0.5);

/* Move in x axis and y axis */
transform: translate(-20px, -20px);

/*Rotate*/
transform: rotate(30deg);

/* skew in x axis and y axis */
transform: skew(40deg, 12deg);

/*default transform origin: 50% along the x axis and 50% along the y axis of the element*/
transform-origin: 270px 20px;
```
