### Arc

```html
a rx,ry rotate large,sweep, endx,endy
```

### Quadratic Curve

```html
q xa,ya endx,endy
```

`t`

### Cubic Curve

```html
c xc1,yc1 xc2,yc2 endx,endy
```

`s`

### flip

```html
<svg width="500" height="500" viewBox="0 0 100 100">
	<path d="M10 10 h30 v30" fill="red"/>
	<path d="M10 10 h30 v30" fill="lightgreen" transform="scale(-1, 1) translate(-100, 0)"/>
	<path d="M10 10 h30 v30" fill="lightblue" transform="scale(1, -1) translate(0, -100)"/>
	<path d="M10 10 h30 v30" fill="orange" transform="scale(-1, -1) translate(-100, -100)"/>
</svg>
```

### animate

```html
<animate 
    attributeName="d"
    values="
      keyframe;
      keyframe2;
      keyframe3
    "
  dur="6s"
  repeatCount="indefinite"/>
```

### defs

```html
<defs>
	<g id="hinge">
		<path .../>
	</g>
</defs>
<use xlink:href="#hinge"/>
```
