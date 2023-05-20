# remark-strip-mdx

This is a fork of the [strip-markdown](https://github.com/remarkjs/strip-markdown) package, but for MDX.

[**remark**][remark] plugin to remove MDX formatting.
This essentially removes everything but paragraphs and text nodes.

## Install

This package is [ESM only](https://gist.github.com/sindresorhus/a39789f98801d908bbc7ff3ecc99d99c):
Node 12+ is needed to use it and it must be `import`ed instead of `require`d.

[npm][]:

```sh
npm install remark-strip-mdx
```

## Use

```js
import { remark } from 'remark'
import remarkMdx from 'remark-mdx'
import strip from 'remark-strip-mdx'

remark()
  .use(remarkMdx)
  .use(strip)
  .process('import Sample from "./sample";\n\nSome _emphasis_, **importance**, and `code`.\n\n<Sample />')
  .then((file) => {
    console.log(String(file))
  })
```

Yields:

```txt
Some emphasis, importance, and code.
```

[remark]: https://github.com/remarkjs/remark

[npm]: https://docs.npmjs.com/cli/install
