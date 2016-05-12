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
