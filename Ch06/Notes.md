## Text shadows with CSS3
- text-shadow: right, left, blur(the distance the shadow travels before fading to nothing), color

```css
/* Simple text shadow */
text-shadow: 1px 1px 1px #ccc;

/* Shadow left and above using negatives */
text-shadow: -4px -4px 0px #dad7d7;

/* Support for HSLA values */
text-shadow: 4px 4px 0px hsla(140, 3%, 26%, 0.4);

/* Omitting the blur value when not needed */
text-shadow: -4px -4px #dad7d7;

/* Multiple text shadows */
text-shadow: 0px 1px #fff,4px 4px 0px #dad7d7;
```

### Box shadows with CSS3
- box-shadow: horizontal offset, vertical offset, blur, spread, color

```css
/* Box shadows */
box-shadow: 0px 3px 5px #444;

/* An inset shadow */
box-shadow: inset 0 0 40px #000;

/* spread extend or contract the shadow in all directions */
.no-spread {
 box-shadow: 0 10px 10px;
}

.spread-contract {
 box-shadow: 0 10px 10px -10px;
}

.spread-expand {
 box-shadow: 0 10px 10px 10px;
}
```

### Background gradients
- background-size:
1. auto: Which sets the element at its native size
2. cover: Which expands the image, preserving its aspect ratio, to cover the area of the element
3. contain: Which expands the image to fit its longest side within the element while preserving the aspect ratio

```css
/* Display liner gradient (top, bottom) */
background: linear-gradient(red, gold);

/* diagonal */
background: linear-gradient(to top right, red, gold);

/* Use degrees */
background: linear-gradient(45deg, red, gold);

/* Circular gradient */
background: radial-gradient(12rem circle at center, yellow, orange, red);

/* Repeating circles
pixel distances between the black, orange, and red colors (0px, 5px, and 10px respectively) */
background: repeating-radial-gradient(black 0px, orange 5px, red 10px);

/* Multiple backgrounds
  + Multiple background sizes */
background: url('../img/1.png'), url('../img/2.png'), url('../img/3.png');
background-size: 60% 50%, 50vw, cover;
background-position: top 50px right 80px, 40px 40px, top center;

/* High-resolution background images */
.bg {
  background-image: url('bg.jpg');
}
@media (min-resolution: 1.5dppx) {
 .bg {
   background-image: url('bg@1_5x.jpg');
 }
}
```
