<h1 align="center">p-charts</h1>

<div align="center">

Chart components based on AntV G2

[![doc][doc-image]][doc-url] [![gitee][gitee-image]][gitee-url] [![Travis status][travis-image]][travis-url] [![antv-g2-deps][antv-g2-image]][antv-g2-url] [![antv-l7-deps][antv-l7-image]][antv-l7-url] [![NPM version][npm-image]][npm-url]

[![GitHub stars][github-starts-image]][github-url] [![GitHub commit activity][github-commit-activity-url]][github-url] [![GitHub top language][github-top-language-image]][vue-url] [![GitHub license][license-image]][github-url]

[travis-image]: https://img.shields.io/travis/silianpan/p-charts
[travis-url]: https://travis-ci.org/github/silianpan/p-charts
[antv-g2-image]: https://img.shields.io/badge/%40antv%2Fg2-v3.5.17-%23873bf4
[antv-g2-url]: https://g2-v3.antv.vision/zh/
[antv-l7-image]: https://img.shields.io/badge/%40antv%2Fl7-latest-4fd431
[antv-l7-url]: https://l7.antv.vision/zh
[npm-image]: https://img.shields.io/npm/v/p-charts
[npm-url]: https://www.npmjs.com/package/p-charts
[github-starts-image]: https://img.shields.io/github/stars/silianpan/p-charts?style=social
[github-url]: https://github.com/silianpan/p-charts
[github-commit-activity-url]: https://img.shields.io/github/commit-activity/m/silianpan/p-charts
[github-top-language-image]: https://img.shields.io/github/languages/top/silianpan/p-charts?color=%234fc08d
[vue-url]: https://vuejs.org/
[license-image]: https://img.shields.io/github/license/silianpan/p-charts
[doc-image]: https://img.shields.io/badge/document-latest-blue
[doc-url]: http://silianpan.cn/p-charts
[gitee-image]: https://gitee.com/twofloor/p-charts/badge/star.svg?theme=dark
[gitee-url]: https://gitee.com/twofloor/p-charts/stargazers

</div>

`p-charts`支持Vue3.x版本，查看分支[vue3](https://github.com/silianpan/p-charts/tree/vue3)

[Document](https://juejin.im/post/6866330015970099208/)

[Blog](http://silianpan.cn/index.php/2020/08/29/p-charts/)

[Examples](http://silianpan.cn/p-charts)

[Gitee](https://gitee.com/twofloor/p-charts)

## Getting Started

### installation

```bash
npm install -S p-charts
# or
yarn add p-charts
```

### Usage

```js
// main.js
import PCharts from 'p-charts'
Vue.use(PCharts)
```

#### p-pie

```html
<template>
  <p-pie
    :data="PieJson"
    :options="options"
    ref="pieRef"
    @pie-title-click="handleTitleClick"
    @pie-label-click="handleLabelClick"
  />
</template>

<script>
import PieJson from './data/pie1.json'
export default {
  data() {
    return {
      PieJson,
      options: {
        fieldMap: {
          time: 'year',
          name: 'budgetSubject',
          // 统计指标，可以更换
          value: 'budgetNum'
        },
        title: `总收入和总支出占比情况-预算数（单位：万元）`,
        colorList: ['#1890ff', '#37c661']
      }
    }
  },
  methods: {
    updateData() {
      this.$refs.pieRef.initData()
    },
    handleTitleClick() {
      console.log('title-click')
    },
    handleLabelClick(data) {
      console.log('label-click', data)
    }
  }
}
</script>
```

## Development

``` bash
# install dependencies
npm install
# or
yarn

# serve with hot reload at localhost:8080
npm run dev
# or
yarn dev

# build for production with minification
npm run build
# or
yarn build
```
