# @peassoft/linter

Oxlint config for PeasSoft projects.

**CAUTION!** This is a highly opinionated config, so you definitely do not want to use it if you are outside the PeasSoft team.

## Organizational Notes

### `oxlint` Installation

This package includes `oxlint` and `oxlint-tsgolint` as its own dependencies. You should not install these packeges into your project.

This is done deliberately. We do not agree with the `oxlint` authors` [versioning policy](https://oxc.rs/docs/guide/usage/linter/versioning.html), especially with what they consider as a **non-breaking** change.

That's why we restricted `oxlint`'s automatic version upgrade to the patch-level. Minor-version changes will be manually reviewed by us, and if a possibility of errors surfacing in previously passing linting code base exists, we will bump the major version of `@peassoft/linter`.

### ESLint Plugins Installation

You should not also install ESlint plugins which are included in the base config. They are subject to the same versioning policy as described above.

However, if you're going to extend the base config with some specific to your project ESLint plugins, you must install them into your project.

## Installation

```shell
$ npm i -D @peassoft/linter
```

## Usage Example

Create `oxlint.config.ts` file in the project root directory.

```ts
import { defineConfig, baseConfig } from '@peassoft/linter';

export default defineConfig({
  extends: [baseConfig],
});
```

Add to your `package.json`:

```json
{
  "scripts": {
    "lint": "oxlint"
  }
}
```
