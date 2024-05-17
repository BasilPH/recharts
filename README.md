# Recharts

[![storybook](https://raw.githubusercontent.com/storybooks/brand/master/badge/badge-storybook.svg)](https://release--63da8268a0da9970db6992aa.chromatic.com/)
[![Build Status](https://github.com/recharts/recharts/workflows/Node.js%20CI/badge.svg)](https://github.com/recharts/recharts/actions)
[![codecov](https://codecov.io/gh/recharts/recharts/graph/badge.svg?token=Bn6L2hrl8T)](https://codecov.io/gh/recharts/recharts)
[![npm version](https://badge.fury.io/js/recharts.svg)](http://badge.fury.io/js/recharts)
[![npm downloads](https://img.shields.io/npm/dm/recharts.svg?style=flat-square)](https://www.npmjs.com/package/recharts)
[![MIT License](https://img.shields.io/badge/license-MIT-blue.svg?style=flat)](/LICENSE)

## Introduction

Recharts is a **Redefined** chart library built with [React](https://facebook.github.io/react/) and [D3](http://d3js.org).

The main purpose of this library is to help you to write charts in React applications without any pain. Main principles of Recharts are:

1. **Simply** deploy with React components.
2. **Native** SVG support, lightweight depending only on some D3 submodules.
3. **Declarative** components, components of charts are purely presentational.

Documentation at [recharts.org](https://recharts.org) and our [storybook (WIP)](https://release--63da8268a0da9970db6992aa.chromatic.com/)

Please see [the wiki](https://github.com/recharts/recharts/wiki) for FAQ.

All development is done on the `master` branch. The current latest release and storybook documentation reflects what is on the `release` branch.

## Examples

```jsx
<LineChart width={400} height={400} data={data} margin={{ top: 5, right: 20, left: 10, bottom: 5 }}>
  <XAxis dataKey="name" />
  <Tooltip />
  <CartesianGrid stroke="#f5f5f5" />
  <Line type="monotone" dataKey="uv" stroke="#ff7300" yAxisId={0} />
  <Line type="monotone" dataKey="pv" stroke="#387908" yAxisId={1} />
</LineChart>
```

All the components of Recharts are clearly separated. The lineChart is composed of x axis, tooltip, grid, and line items, and each of them is an independent React Component. The clear separation and composition of components is one of the principle Recharts follows.

## Installation

### npm

NPM is the easiest and fastest way to get started using Recharts. It is also the recommended installation method when building single-page applications (SPAs). It pairs nicely with a CommonJS module bundler such as Webpack.

```sh
# latest stable
$ npm install recharts react-is
```

`react-is` needs to match the version of your installed `react` package.

### umd

The UMD build is also available on unpkg.com:

```html
<script src="https://unpkg.com/react/umd/react.production.min.js"></script>
<script src="https://unpkg.com/react-dom/umd/react-dom.production.min.js"></script>
<script src="https://unpkg.com/react-is/umd/react-is.production.min.js"></script>
<script src="https://unpkg.com/recharts/umd/Recharts.min.js"></script>
```

Then you can find the library on `window.Recharts`.

### dev build

```sh
$ git clone https://github.com/recharts/recharts.git
$ cd recharts
$ npm install
$ npm run build
```

## Demo

To examine the demos in your local build, execute:

```sh
$ npm run[-script] demo
```

and then browse to http://localhost:3000.

## Storybook

We are in the process of unifying documentation and examples in storybook. To run it locally, execute

```sh
$ npm run[-script] storybook
```

and then browse to http://localhost:6006.

## Releases

[Releases](https://github.com/recharts/recharts/releases) are automated via GH Actions - when a new release is created in GH, CI will trigger that:

1. Runs a build
2. Runs tests
3. Runs `npm publish`

Version increments and tagging are not automated at this time.

### Release testing

Until we can automate more, it should be preferred to test as close to the results of `npm publish` as we possibly can. This ensures we don't publish unintended breaking changes. One way to do that is using `yalc` - `npm i -g yalc`.

1. Make your changes in recharts
2. `yalc publish` in recharts
3. `yalc add recharts` in your test package (ex: in a vite or webpack reach app with recharts installed, imported, and your recent changes used)
4. `npm install`
5. Test a local run, a build, etc.

## Module Formats

- [babel-plugin-recharts](https://github.com/recharts/babel-plugin-recharts) A simple transform to cherry-pick Recharts modules so you don’t have to. **Note: this plugin is out of date and may not work with 2.x**

## Thanks

<a href="https://www.chromatic.com/"><img src="https://user-images.githubusercontent.com/321738/84662277-e3db4f80-af1b-11ea-88f5-91d67a5e59f6.png" width="153" height="30" alt="Chromatic" /></a>

Thanks to [Chromatic](https://www.chromatic.com/) for providing the visual testing platform that helps us review UI changes and catch visual regressions.

## License

[MIT](http://opensource.org/licenses/MIT)

Copyright (c) 2015-2024 Recharts Group.
