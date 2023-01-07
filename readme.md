# `esbuild-plugin-linter`

[![latest version on npm](https://img.shields.io/npm/v/esbuild-plugin-linter)](https://www.npmjs.com/package/esbuild-plugin-linter)
[![npm downloads a month](https://img.shields.io/npm/dm/esbuild-plugin-linter)](https://www.npmjs.com/package/esbuild-plugin-linter)
[![required node version](https://img.shields.io/node/v/esbuild-plugin-linter)](https://github.com/nodejs/Release)
[![esbuild peer dep](https://img.shields.io/npm/dependency-version/esbuild-plugin-linter/peer/esbuild?label=esbuild%20peer%20dep)](https://github.com/evanw/esbuild)
[![eslint peer dep](https://img.shields.io/npm/dependency-version/esbuild-plugin-linter/peer/eslint?label=eslint%20peer%20dep)](https://github.com/eslint/eslint)
[![package license](https://img.shields.io/npm/l/esbuild-plugin-linter)](license)

> Lint your [`esbuild`](https://github.com/evanw/esbuild) bundles with [`eslint`](https://github.com/eslint/eslint). 🧐

Nicely integrates the most recent version of [`eslint`](https://github.com/eslint/eslint) into an [`esbuild`](https://github.com/evanw/esbuild) plugin.

## How

```bash
yarn add esbuild-plugin-linter --dev
```

```js
const { build } = require('esbuild');
const eslint = require('esbuild-plugin-linter');

build({
  // ...
  plugins: [
    eslint({ /* config */ })
  ]
})
```

## Config

This plugin respects your [ESLint configuration](https://eslint.org/docs/user-guide/configuring) as per default. It also takes a configuration object intended for the [ESLint constructor](https://eslint.org/docs/latest/developer-guide/nodejs-api#parameters) with the addition of a `filter` property. The most important options are:

### `filter`

Type: `RegExp`<br>
Default: `/\.(jsx?|tsx?|vue|svelte)$/`<br>
Used by: [`esbuild`](https://github.com/evanw/esbuild)<br>
Reference: [esbuild.github.io](https://esbuild.github.io/plugins/#on-load-options)

Instructs `esbuild` what files to look at. Only files matching this pattern will be looked at.

### `fix`

Type: `boolean`<br>
Default: `false`<br>
Used by: [`eslint`](https://github.com/eslint/eslint)<br>
Reference: [eslint.org (`options.fix`)](https://eslint.org/docs/latest/developer-guide/nodejs-api#parameters)<br>

Controls whether to enable or disable the autofix feature of ESLint.

### `useEslintrc`

Type: `boolean`<br>
Default: `true`<br>
Used by: [`eslint`](https://github.com/eslint/eslint)<br>
Reference: [eslint.org (`options.useEslintrc`)](https://eslint.org/docs/latest/developer-guide/nodejs-api#parameters)<br>

If set to `false`, ESLint will not respect any configuration files it finds.

## License

MIT
