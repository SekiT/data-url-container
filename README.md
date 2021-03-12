# Data URL container

My experiment to generate URL that begins with `https://` and can be any HTML.

## Usage

Use [generator](https://SekiT.github.io/data-url-container/generator.html) to make a link for any HTML content.

## How it works

You can make a data URL for HTML:

```js
const toURL = (html) => `data:text/html;base64,${btoa(html)}`

toURL(`<html><body>foo</body></html>`)
// => data:text/html;base64,PGh0bWw+PGJvZHk+Zm9vPC9ib2R5PjwvaHRtbD4=
```

Surprisingly, `<iframe>` accepts such URL as `src`.

`index.html` just read the query string and open that in `<iframe>`.
