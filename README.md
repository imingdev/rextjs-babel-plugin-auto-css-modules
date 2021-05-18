# @rextjs/babel-plugin-auto-css-modules

Automatically identify CSS Modules

```js
import styles from 'a.scss'; //===>import styles from 'a.scss?modules'
```

## Usage

Without options:

```json
{
  "plugins": [
    "@rextjs/babel-plugin-auto-css-modules"
  ]
}
```

With options:

```json
{
  "plugins": [
    [
      "@rextjs/babel-plugin-auto-css-modules",
      {
        "generate": "function"
      }
    ]
  ]
}
```

## Options

### `generate type function`

```js
(value, suffix) => {
  const CSS_EXT_NAMES = ['.css', '.less', '.sass', '.scss', '.stylus', '.styl'];
  if (CSS_EXT_NAMES.includes(suffix)) return `${value}?modules`;
}
// return import styles from 'a.scss?modules'
```
