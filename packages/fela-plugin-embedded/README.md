# fela-plugin-embedded

<img alt="npm version" src="https://badge.fury.io/js/fela-plugin-embedded.svg"> <img alt="npm downloads" src="https://img.shields.io/npm/dm/fela-plugin-embedded.svg">

This plugins allows the use of inline keyframes and font-faces. It directly resolves them while rendering and only returns the correct reference.

## Installation
```sh
yarn add fela-plugin-embedded
```
You may alternatively use `npm i --save fela-plugin-embedded`.

## Usage
Make sure to read the documentation on [how to use plugins](http://fela.js.org/docs/advanced/Plugins.html).

```javascript
import { createRenderer } from 'fela'
import embedded from 'fela-plugin-embedded'

const renderer = createRenderer({
  plugins: [ embedded() ]
})
```

## Example
#### Input
```javascript
{
  width: '25px',
  animationName: {
    '0%': { color: 'red ' },
    '100%': { color: 'blue' }
  },
  fontFace: {
    fontFamily: 'Arial',
    src: [
      '../Arial.svg',
      '../Arial.ttf'
    ]
  }
}
```
#### Output
```javascript
{
  width: '25px',
  animationName: 'k1',
  fontFamily: 'Arial'
}
```

### Base64 encoded font-faces

```javascript
{
  fontFace: {
    fontFamily: 'font-name',
    src: [
      'data:application/x-font-woff;charset=utf-8;base64,PASTE-BASE64-HERE'
    ]
  }
}
```

### Multiple font-faces

```javascript
{
  fontFace: [{
      fontFamily: 'Arial',
      fontWeight: 400
      src: [
        'arial-regular.svg',
        'arial-regular.ttf'
      ]
    },
    {
      fontFamily: 'Arial',
      fontWeight: 700,
      src: [
        'arial-bold.svg', 
        'arial-bold.ttf'
      ]
    }]
}
```

## License
Fela is licensed under the [MIT License](http://opensource.org/licenses/MIT).<br>
Documentation is licensed under [Creative Common License](http://creativecommons.org/licenses/by/4.0/).<br>
Created with ♥ by [@rofrischmann](http://rofrischmann.de) and all the great contributors.
