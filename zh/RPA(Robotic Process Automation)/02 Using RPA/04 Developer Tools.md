---
title: 04 Developer Tools
tags:
  - Document
  - Tutorial
  - Using RPA
description: >-
  我们提供开发者工具来帮助用户抓取云手机视图树。您可以连接到我们的云手机，轻松获取View
  Tree的结构和内容。编辑模板时重要节点中使用的一些必要信息依赖于调试工具中的元素属性。
---
# 开发者工具

我们提供开发者工具来帮助用户抓取云手机视图树。您可以连接到我们的云手机，轻松获取View Tree的结构和内容。编辑模板时重要节点中使用的一些必要信息依赖于调试工具中的元素属性。

## 步骤1：编辑模板中选择云手机

创建或修改模板时，点击右上角“选择云手机”。

## 第二步：打开云手机调试器

1.选择云手机后，在右上角打开当前的云手机。
2、云手机启动后，点击<img src="../image/debug_icon.png" style="width:30px; height:30px;vertical-align: middle; margin:0 2px;" /> 按钮进入调试器。

<img src="../image/enter_debug.png" style="width:1400px; height:400px;vertical-align: middle; margin:0 2px; border: 1pxsolid #D9D9D9;"/>

<br>

<img src="../image/phone_debug.png" style="width:1400px; height:400px; 垂直对齐: 中间; margin:0 2px; 边框: 1px 实线#D9D9D9;"/>

## 如何使用调试器？

1. **快照模式**
    1. 点击“创建快照”，调试器工具将保存当前云手机页面的UI树。
    2. 快照模式下，将鼠标悬停在左侧云手机屏幕上会显示红色框，右侧 UI 树会突出显示相应的 DOM 元素。
    3. 快照模式下，页面不可点击交互，下方虚拟按钮也被禁用。

2. **关闭快照模式**
    1. 单击调试器工具右上角的“快照模式”开关，关闭快照模式。
    2. 关闭快照模式后，手机和虚拟按钮恢复工作。

## 元素属性说明

- **X**：元素在 X 轴上的中心点位置。
- **Y**：元素在 Y 轴上的中心点位置。
- **bounds**：元素左上角和右下角的坐标，例如“[789,96][1038,404]”。
    - 相关节点：[Tap(x, y)](../03%20Node/01%20Simulation%20Operations/05%20Tap(x,%20y).md)
- **文本**：控件上可见的文本内容，通常是用户可以直接看到的文本。
- **fullID**：在Android开发中，开发者设置的ID如`android:id="@+id/btn_submit"`。 fullID 是包含包名称的完整形式（例如“com.example.app:id/btn_submit”）。
- **class**：控件的Android系统类名，代表控件的“类型”（例如按钮、文本框、列表等）。
- **desc**：控件的描述文本，也称为“内容描述”，主要用于辅助功能（例如屏幕阅读器）。
    - 相关节点：[查找元素](../03%20Node/01%20Simulation%20Operations/03%20Find%20Element.md)、[点击元素](../03%20Node/01%20Simulation%20Operations/04%20Tap%20Element.md)
- **package**：Android系统分配给每个应用程序的唯一标识符，通常采用“反向域名+应用程序标识符”的格式（例如`com.taobao.taobao`、`com.tencent.mm`）。它本质上是Android设备中每个App的“身份证号”。
    - 相关节点：[启动APP](../03%20Node/01%20Simulation%20Operations/01%20Launch%20APP.md)、[关闭APP](../03%20Node/01%20Simulation%20Operations/02%20Close%20APP.md)
