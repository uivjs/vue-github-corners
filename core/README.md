@uivjs/vue-github-corners
===

[![Build & Deploy](https://github.com/uivjs/vue-github-corners/actions/workflows/ci.yml/badge.svg)](https://github.com/uivjs/vue-github-corners/actions/workflows/ci.yml)
[![Downloads](https://img.shields.io/npm/dm/@uivjs/vue-github-corners.svg?style=flat)](https://www.npmjs.com/package/@uivjs/vue-github-corners)
[![npm version](https://img.shields.io/npm/v/@uivjs/vue-github-corners.svg)](https://www.npmjs.com/package/@uivjs/vue-github-corners)
[![npm unpkg](https://img.shields.io/badge/Open%20in-unpkg-blue)](https://uiwjs.github.io/npm-unpkg/#/pkg/@uivjs/vue-github-corners/file/README.md)

Add a Github corner to your project page, This GitHub corner for Vue 3.0+ component.

## Install

```bash
npm i @uivjs/vue-github-corners
```

## Usage

```vue
<template>
  <div>
    <github-corners fixed target="__blank" href="https://github.com/uivjs/vue-github-corners" />
  </div>
</template>

<script>
import { defineComponent } from 'vue';
import GithubCorners from '@uivjs/vue-github-corners';

export default defineComponent({
  components: {
    GithubCorners
  }
});
</script>
```

## API

- `href` The link to your project page.
- `size` Default: `80`, The width and height of the corner.
- `color` Default: `#fff`, The Github logo color of the corner.
- `bgColor` Default: `#151513`, The background color of the corner.
- `position: PropType<'right' | 'left'>` Default: `right`, The position of corner. 
- `fixed` Default `false`, It is positioned relative to the initial containing block established.
- `zIndex` Sets the z-order of a positioned element and its descendants or flex items.
- `bottom` Is it displayed at the bottom? 

## Related

- [react-github-corners](https://github.com/uiwjs/react-github-corners) Add a Github corner to your project page, This GitHub corner for react component. 

## License

Licensed under the MIT License.
