# JavaScript: Dynamic Contrast
Return suggested contrast color (dark or light) for the color (hex/rgba) given.

## Demo
[Check it out](https://julianrichen.github.io/javascript-dynamic-contrast)

A demo showing dynamiclly loaded color sqaures with text that is either white or black, which ever gives the best contrast.

## Usage
Include the JS file
```html
<script type="text/javascript" src="/path/to/src/dynamic-contrast.js"></script>
```

Use the `getColorContrast()` function to return "light" or "dark" (the recommended text brightness).
```js
console.log(getColorContrast("#000")); // light
console.log(getColorContrast("#000000")); // light
console.log(getColorContrast("000")); // light
console.log(getColorContrast("000000")); // light
console.log(getColorContrast("rgb(255, 255, 255)")); // dark
console.log(getColorContrast("rgb(255, 255, 255")); // dark
console.log(getColorContrast("rgb( 255 , 255 , 255 )")); // dark
console.log(getColorContrast("rgb(17, 17, 17)")); // light
console.log(getColorContrast("rgb(30, 30, 30)")); // light
console.log(getColorContrast("rgba(255, 255, 255)")); // dark
console.log(getColorContrast("rgba(255, 255, 255, 1)")); // dark
console.log(getColorContrast("rgba(255, 255, 255, .5)")); // dark
console.log(getColorContrast("rgba( 255 , 255 , 255 , 1)")); // dark
```

## Example
Select the users custom background `#users_bg`, get the background color & then set the the class of the background to `light-text` if the background will be too dark for normal text.
```js
var bg      = document.getElementById("users_bg"),
    bgColor = bg.style.backgroundColor;

if(getColorContrast(bgColor) == "light") {
    bg.setAttribute("class", "light-text");
}

```

