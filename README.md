# Best Practices

A compilation of best practices I've found or ones I've come to with experience.

### Table of contents

- [Property Order in CSS](#property-order-in-css)
- [Font Integration in CSS](#font-integration-in-css)
- [Favicon Connection](#favicon-connection)

## Property Order in CSS

Observe a certain order of styles for the convenience and readability of the code. Positioning properties come first, then block model properties, then fonts. At the very end, other styling and animations.

```css
.element {
  /* Positioning */
  position: relative;
  left: 0;
  right: 0;
  top: 0;
  bottom: 0;

  /* Block model */
  display: flex;
  align-items: center;
  margin: 10px;
  padding: 10px 20px;
  border: 1px solid red;
  width: 200px;
  height: 100px;
  box-sizing: border-box;

  /* Fonts */
  font-family: Arial;
  font-size: 25px;
  font-style: italic;
  text-decoration: none;
  color: red;

  /* Styling */
  background: red;
  opacity: 1;

  /* Animations */
  transform: translateX(5px);
  animation: shake 0.3s infinite;
}
```

## Font Integration in CSS

Modern integration of locally installed fonts into CSS.

### Normal

```css
@font-face {
  font-family: 'Rubik';
  font-display: swap;
  font-style: normal;
  font-weight: normal;
  src: url('rubik-regular.woff2') format('woff2'),
       url('rubik-regular.woff') format('woff');
}
```

### Italic

```css
@font-face {
  font-family: 'Rubik';
  font-display: swap;
  font-style: italic;
  font-weight: normal;
  src: url('rubik-italic.woff2') format('woff2'),
       url('rubik-italic.woff') format('woff');
}
```

### Bold

```css
@font-face {
  font-family: 'Rubik';
  font-display: swap;
  font-style: normal;
  font-weight: bold;
  src: url('rubik-bold.woff2') format('woff2'),
       url('rubik-bold.woff') format('woff');
}
```

### Usage

```css
body {
  font-family: 'Rubik', sans-serif;
}

h2 {
  font-weight: bold;
}
```

## Favicon Connection

Connecting the favicon the right way ([source](https://evilmartians.com/chronicles/how-to-favicon-in-2021-six-files-that-fit-most-needs)).

### For the browser using HTML

```html
<link rel="icon" href="/favicon.ico" sizes="32x32">
<link rel="icon" href="/icon.svg" type="image/svg+xml">
<link rel="apple-touch-icon" href="/apple-touch-icon.png"> <!-- 180×180 -->
<link rel="manifest" href="/manifest.webmanifest">
```

### And in your web app manifest

```json
// manifest.webmanifest
{
  "icons": [
    { "src": "/icon-192.png", "type": "image/png", "sizes": "192x192" },
    { "src": "/icon-512.png", "type": "image/png", "sizes": "512x512" }
  ]
}
```
