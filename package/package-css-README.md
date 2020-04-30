# CSS

## rollup-plugin-css-only

讓 svelte 支援在 script import css

```
npm i rollup-plugin-css-only --save-dev
```

安裝套件完後，在 `rollup.config.js` 設定檔案中的 `plugins` 加入 `css` 的函式，並指定輸出的目錄在 `output` 參數中，預設輸出的檔案位置為與 `rollup.config.js` 同個目錄

```
// rollup.config.js
import css from 'rollup-plugin-css-only'

export default {
  entry: 'entry.js',
  dest: 'bundle.js',
  plugins: [
    css({ output: './custom-bundle.css' })
  ]
}
```

設定完後在 `<script>` 標籤中即可直接 import CSS 檔案，這樣所有的 CSS 即會被輸出至 `./custom-bundle.css`

```html
<script>
// entry.js
import './reset.css'
import './layout.css'
</script>
```

*參考資料*
* [rollup-plugin-css-only - npm](https://www.npmjs.com/package/rollup-plugin-css-only)
* [thgh/rollup-plugin-css-only: Rollup plugin that bundles imported css](https://github.com/thgh/rollup-plugin-css-only)

## rollup-plugin-sass

讓 svelte 支援在 script import sass

*參考資料*
* [differui/rollup-plugin-sass: Roll .sass files.](https://github.com/differui/rollup-plugin-sass)