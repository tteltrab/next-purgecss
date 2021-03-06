# next-purgecss

Next.js + Purgecss = 🔥

[Next.js](https://nextjs.org/) makes it easy to create SSR and static React applications.

[Purgecss](https://www.purgecss.com/) helps you remove unused CSS.

## Installation

### 1. Install the packages

`next-purgecss` requires one of the following **css next plugins** :

- [next-css](https://github.com/zeit/next-plugins/tree/master/packages/next-css)
- [next-less](https://github.com/zeit/next-plugins/tree/master/packages/next-less)
- [next-sass](https://github.com/zeit/next-plugins/tree/master/packages/next-sass)

Just pick the one that fits your needs. In the following steps, I will use `next-css` but it works the same for the other **css next plugins**.

For example, install `next-css` and `next-purgecss` :

```
yarn add @zeit/next-css next-purgecss --dev
```

or with npm :

```
npm install @zeit/next-css next-purgecss --save-dev
```

### 2. Edit `next.config.js`.

```js
// next.config.js
const withCss = require('@zeit/next-css')
const withPurgeCss = require('next-purgecss')

module.exports = withCss(withPurgeCss())
```

## Options

By default, this plugin will scan `components` and `pages`
directories for classnames.

You can pass custom options to
[Purgecss](https://github.com/FullHuman/purgecss-webpack-plugin) by defining
`purgeCss` object in your `next.config.js`.

```js
// next.config.js
module.exports = withCss(
  withPurgeCss({
    purgeCss: {
      whitelist: () => ['my-custom-class']
    }
  })
)
```

The list of available options are documented in [`purgecss-webpack-plugin`
docs](https://github.com/FullHuman/purgecss-webpack-plugin#options).
