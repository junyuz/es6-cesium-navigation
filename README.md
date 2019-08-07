# es6-cesium-navigation

Cesium 插件，它为 Cesium 地图添加了一个用户友好的指南针，导航器（放大/缩小），以及距离尺度图形用户界面。

在原作者基础上 ES6 化更彻底，方便引用打包后的 Cesium 使用。

## 示例

- [CesiumNavigation](https://github.com/zouyaoji/vue-cesium/blob/master/src/components/tools/CesiumNavigation.vue)

- [CesiumNavigation-Demo](https://zouyaoji.top/vue-cesium/#/zh/tools/CesiumNavigation)

## 快速开始

```bash
npm install es6-cesium-navigation --save
```

使用该库的前提是已经引入了 Cesium.js，如[vue-cesium](https://github.com/zouyaoji/vue-cesium)使用方式。

```html
<template>
  <cesium-viewer @ready="ready"></cesium-viewer>
</template>
<script>
  import CesiumNavigation from 'es6-cesium-navigation'
  export default {
    data() {
      return {}
    },
    methods: {
      ready(cesiumInstance) {
        const { Cesium, viewer } = cesiumInstance
        // 在这儿获取Cesium和viewer实例，再执行相关逻辑代码
        var options = {
          // 用于在使用重置导航重置地图视图时设置默认视图控制。接受的值是Cesium.Cartographic 和 Cesium.Rectangle.
          defaultResetView: Cesium.Rectangle.fromDegrees(80, 22, 130, 50),
          // 用于启用或禁用罗盘。true是启用罗盘，false是禁用罗盘。默认值为true。如果将选项设置为false，则罗盘将不会添加到地图中。
          enableCompass: true,
          // 用于启用或禁用缩放控件。true是启用，false是禁用。默认值为true。如果将选项设置为false，则缩放控件将不会添加到地图中。
          enableZoomControls: false,
          // 用于启用或禁用距离图例。true是启用，false是禁用。默认值为true。如果将选项设置为false，距离图例将不会添加到地图中。
          enableDistanceLegend: false,
          // 用于启用或禁用指南针外环。true是启用，false是禁用。默认值为true。如果将选项设置为false，则该环将可见但无效。
          enableCompassOuterRing: true
        }
        let cesiumNavigation = new CesiumNavigation(viewer, options)
      }
    }
  }
</script>
```

### 参考

[cesium-navigation-es6](https://github.com/richard1015/cesium-navigation-es6)
