# es6-cesium-navigation

Cesium 插件，它为 Cesium 地图添加了一个用户友好的指南针，导航器（放大/缩小），以及距离尺度图形用户界面。

在原作者基础上 ES6 化更彻底，方便引用打包后的 Cesium 使用。

## Demo

## QuickStart

```bash
npm install cesium-navigation-es6 --save
```

```HTML
<template>
  <div id="cesiumContainer"></div>
</template>
<script type="text/javascript">
import Cesium from "cesium/Cesium";
import "cesium/Widgets/widgets.css";
import CesiumNavigation from "cesium-navigation-es6";

var options = {};
// 用于在使用重置导航重置地图视图时设置默认视图控制。接受的值是Cesium.Cartographic 和 Cesium.Rectangle.
options.defaultResetView = Cesium.Rectangle.fromDegrees(80, 22, 130, 50);
// 用于启用或禁用罗盘。true是启用罗盘，false是禁用罗盘。默认值为true。如果将选项设置为false，则罗盘将不会添加到地图中。
options.enableCompass= true;
// 用于启用或禁用缩放控件。true是启用，false是禁用。默认值为true。如果将选项设置为false，则缩放控件将不会添加到地图中。
options.enableZoomControls= false;
// 用于启用或禁用距离图例。true是启用，false是禁用。默认值为true。如果将选项设置为false，距离图例将不会添加到地图中。
options.enableDistanceLegend= false;
// 用于启用或禁用指南针外环。true是启用，false是禁用。默认值为true。如果将选项设置为false，则该环将可见但无效。
options.enableCompassOuterRing= true;

let viewer = new Cesium.Viewer("cesiumContainer");
CesiumNavigation(viewer, options);
```

### 参考文章
