# Data URL container

My experiment to generate URL that begins with `https://` and can be any HTML.

## Usage

1. Generate base64-encoded HTML string:

  ```js
  btoa(`<html><body>foo</body></html>`)
  // => "PGh0bWw+PGJvZHk+Zm9vPC9ib2R5PjwvaHRtbD4="
```

2. Open index.html of this repo with that string in query:

  https://SekiT.github.io/data-url-container/index.html?PGh0bWw+PGJvZHk+Zm9vPC9ib2R5PjwvaHRtbD4=

  All you need is prepend `https://SekiT.github.io/data-url-container/index.html?` to that string

## Method

You can make a data URL for HTML:

```js
const toURL = (html) => `data:text/html;base64,${btoa(html)}`

toURL(`<html><body>foo</body></html>`)
// => data:text/html;base64,PGh0bWw+PGJvZHk+Zm9vPC9ib2R5PjwvaHRtbD4=
```

Surprisingly, `<iframe>` accepts such URL as `src`.

`index.html` just read the query string and open that in `<iframe>`.
