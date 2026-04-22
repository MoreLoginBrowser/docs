---
title: 03 Find Element
tags:
  - Document
  - Tutorial
  - Simulation Operations
description: 1. 在当前页面找到视图树元素，然后通过 Tap Element 节点点击该元素
---
# 查找元素 

您可以对当前节点执行以下操作：
1. 在当前页面找到视图树元素，然后通过 [Tap Element](../01%20Simulation%20Operations/04%20Tap%20Element.md) 节点点击该元素
2. 找到特定的视图树元素，然后通过 [Run JS Script](../02%20Data%20Processing/01%20Run%20JS%20Script.md) 节点获取该元素的属性
3. 找到特定的视图树元素，然后通过当前节点的输出检查该元素是否存在，类似于打印调试中打印日志

[什么是视图树？](../../05%20附录/02%20What%20is%20a%20view%20tree%3F.md)

## 参数

- **选择器类型**下拉菜单
    - 通过查找元素
    - 使用上一个元素

如果选择“按查找元素”，则可以通过以下 DOM 节点条件过滤元素。符合您设置的属性条件的元素将被执行器过滤掉。

- 您可以在**[满足条件时]**中添加所需条件。支持以下4种条件，最多同时支持4个并行过滤器：
    - 文字
    - 完整ID
    - 类
    - 描述

    您可以通过开发者工具获取当前云手机屏幕的元素属性。


- **[当页面上有多个匹配对象时]**

    - 获取单个元素
      - **[选择哪个元素？]**
        - 当选择“获取单个元素”时，会出现此选项。您可以输入相应的索引号，例如输入数字1表示您将获得第一个匹配的元素
    - 获取元素列表


“使用上一个元素”：直接匹配实际执行时元素的DOM节点。此功能通常与“查找元素”节点一起使用。

- **元素出现的最长等待时间**
    - 填写数字后，当前查找器将轮询您需要查找的元素。找到元素后继续执行。如果在这段时间内没有找到该元素，则开始执行下一个节点。
    - 可以填写或引用一个数字，单位是毫秒。

- **[查找元素后延迟]**

## 输出

- **输出参数**
    - Element：以节点格式输出（实际上是JSON）。您可以通过执行“运行JS脚本”直接解析元素中的内容。


- **执行日志**
    - 开始时间
    - 结束时间
    - 持续时间（毫秒）
    - 状态（成功/失败）

## 示例

1、在Android系统的APP列表页面，可以通过Find Element节点输出每个APP的DOM元素。下一步，您可以通过 Loop 节点迭代每个 APP 的 DOM 元素，然后通过 Run JS Script 节点检查每个 APP 的名称。

    #### 配置：

    |字段名称 |字段值 |
    | -------------------------------------------------------------------- | ----------------------------------------------------------- |
    | **当条件满足时** | “fullID”等于“com.android.launcher3:id/icon”|
    | **当页面上有多个匹配对象时** |获取元素列表 |
    | **等待元素出现超时** | 3000 | 3000
    | **查找元素后延迟** | 0 |

    #### 输出：

    ##### 输出参数

    “**元素列表**”是一个具有以下值的列表：

    <详情>
    <summary>点击展开/折叠</summary>
    [ { "isScrollable": false, "centerX": 135, "uuid": "1b03ee9a-91bd-457f-9981-7f2bfba0905b", "isLongClickable": true, "resourceId": "com.android.launcher3:id/icon", "index": 0, "isCheckable": false, "childCount": 0, "bounds": { "top": 261, "right": 270, "left": 0, "bottom": 621 }, "packageName": "com.android.launcher3", "isSelected": false, "isFocusable": true, "isPassword": false, "contentDescription": "日历", "isClickable": true, "isChecked": false, “isFocused”：假，“isEnabled”：真，“className”：“和

[翻译服务截断：以下为未翻译的原始内容]

roid.widget.TextView", "centerY": 441, "text": "Calendar", "isVisibleToUser": true }, { "isScrollable": false, "text": "Chrome", "isLongClickable": true, "resourceId": "com.android.launcher3:id/icon", "index": 1, "isCheckable": false, "uuid": "6446a15a-47e9-4ee3-adcd-8f63197653d4", "childCount": 0, "contentDescription": "Chrome", "packageName": "com.android.launcher3", "isSelected": false, "bounds": { "top": 261, "right": 540, "bottom": 621, "left": 270 }, "centerX": 405, "isFocusable": true, "isPassword": false, "isClickable": true, "isChecked": false, "isFocused": false, "isEnabled": true, "className": "android.widget.TextView", "centerY": 441, "isVisibleToUser": true }, { "isScrollable": false, "centerX": 675, "isLongClickable": true, "resourceId": "com.android.launcher3:id/icon", "uuid": "d5ae8607-be23-4166-a332-32911dc5eae0", "isCheckable": false, "childCount": 0, "index": 2, "packageName": "com.android.launcher3", "isSelected": false, "isFocusable": true, "isPassword": false, "isClickable": true, "text": "Clock", "isChecked": false, "isFocused": false, "isEnabled": true, "className": "android.widget.TextView", "contentDescription": "Clock", "centerY": 441, "bounds": { "right": 810, "top": 261, "left": 540, "bottom": 621 }, "isVisibleToUser": true }, { "isScrollable": false, "contentDescription": "Contacts", "isLongClickable": true, "resourceId": "com.android.launcher3:id/icon", "isCheckable": false, "index": 3, "childCount": 0, "packageName": "com.android.launcher3", "isSelected": false, "text": "Contacts", "isFocusable": true, "isPassword": false, "centerX": 945, "uuid": "6f920c6c-221c-425c-b5b1-d438b1fc7fe9", "isClickable": true, "isChecked": false, "isFocused": false, "isEnabled": true, "className": "android.widget.TextView", "centerY": 441, "bounds": { "top": 261, "right": 1080, "bottom": 621, "left": 810 }, "isVisibleToUser": true }, { "isScrollable": false, "centerX": 135, "centerY": 801, "bounds": { "bottom": 981, "right": 270, "left": 0, "top": 621 }, "isLongClickable": true, "text": "Files", "resourceId": "com.android.launcher3:id/icon", "contentDescription": "Files", "isCheckable": false, "childCount": 0, "packageName": "com.android.launcher3", "index": 4, "isSelected": false, "isFocusable": true, "isPassword": false, "isClickable": true, "isChecked": false, "isFocused": false, "isEnabled": true, "className": "android.widget.TextView", "uuid": "3e8b09e7-4948-4132-9ca8-0ca57cf5a12d", "isVisibleToUser": true }, { "isScrollable": false, "contentDescription": "Gallery", "centerY": 801, "isLongClickable": true, "resourceId": "com.android.launcher3:id/icon", "isCheckable": false, "childCount": 0, "index": 5, "text": "Gallery", "packageName": "com.android.launcher3", "isSelected": false, "centerX": 405, "isFocusable": true, "isPassword": false, "isClickable": true, "isChecked": false, "isFocused": false, "isEnabled": true, "className": "android.widget.TextView", "uuid": "7b1b7b09-3ca0-422d-b35a-37ce26e2517b", "isVisibleToUser": true, "bounds": { "bottom": 981, "right": 540, "top": 621, "left": 270 } }, { "isScrollable": false, "centerY": 801, "centerX": 675, "isLongClickable": true, "resourceId": "com.android.launcher3:id/icon", "isCheckable": false, "childCount": 0, "packageName": "com.android.launcher3", "isSelected": false, "bounds": { "right": 810, "bottom": 981, "top": 621, "left": 540 }, "index": 6, "contentDescription": "Gmail", "uuid": "9b8815b9-1079-4969-bf77-c3b27e4656f0", "isFocusable": true, "isPassword": false, "isClickable": true, "isChecked": false, "isFocused": false, "isEnabled": true, "className": "android.widget.TextView", "isVisibleToUser": true, "text": "Gmail" }, { "isScrollable": false, "text": "Instagram", "centerY": 801, "uuid": "045888d5-9154-4a2a-b6da-649f6c54e9da", "isLongClickable": true, "resourceId": "com.android.launcher3:id/icon", "bounds": { "bottom": 981, "right": 1080, "top": 621, "left": 810 }, "isCheckable": false, "childCount": 0, "contentDescription": "Instagram", "packageName": "com.android.launcher3", "isSelected": false, "index": 7, "isFocusable": true, "isPassword": false, "centerX": 945, "isClickable": true, "isChecked": false, "isFocused": false, "isEnabled": true, "className": "android.widget.TextView", "isVisibleToUser": true }, { "isScrollable": false, "index": 8, "uuid": "4ad6d1e9-02a4-4163-968b-b764968a2e1b", "centerX": 135, "text": "Messaging", "isLongClickable": true, "bounds": { "top": 981, "right": 270, "left": 0, "bottom": 1341 }, "resourceId": "com.android.launcher3:id/icon", "isCheckable": false, "childCount": 0, "centerY": 1161, "contentDescription": "Messaging", "packageName": "com.android.launcher3", "isSelected": false, "isFocusable": true, "isPassword": false, "isClickable": true, "isChecked": false, "isFocused": false, "isEnabled": true, "className": "android.widget.TextView", "isVisibleToUser": true }, { "isScrollable": false, "index": 9, "text": "MoreLogin Bot", "isLongClickable": true, "resourceId": "com.android.launcher3:id/icon", "isCheckable": false, "childCount": 0, "centerY": 1161, "packageName": "com.android.launcher3", "isSelected": false, "contentDescription": "MoreLogin Bot", "centerX": 405, "isFocusable": true, "isPassword": false, "isClickable": true, "uuid": "fa990303-fa24-4c27-bc1b-32dec1d15fc7", "bounds": { "top": 981, "right": 540, "bottom": 1341, "left": 270 }, "isChecked": false, "isFocused": false, "isEnabled": true, "className": "android.widget.TextView", "isVisibleToUser": true }, { "isScrollable": false, "index": 10, "bounds": { "right": 810, "top": 981, "left": 540, "bottom": 1341 }, "centerX": 675, "isLongClickable": true, "resourceId": "com.android.launcher3:id/icon", "isCheckable": false, "childCount": 0, "centerY": 1161, "packageName": "com.android.launcher3", "isSelected": false, "isFocusable": true, "isPassword": false, "isClickable": true, "contentDescription": "Open Camera", "isChecked": false, "isFocused": false, "isEnabled": true, "className": "android.widget.TextView", "text": "Open Camera", "uuid": "55fd0ae2-cb1b-44f9-93af-91064aaebea2", "isVisibleToUser": true }, { "isScrollable": false, "index": 11, "contentDescription": "Phone", "bounds": { "top": 981, "right": 1080, "bottom": 1341, "left": 810 }, "isLongClickable": true, "resourceId": "com.android.launcher3:id/icon", "uuid": "355737cc-e262-4c9a-872a-79ce9ff01bdd", "isCheckable": false, "childCount": 0, "centerY": 1161, "packageName": "com.android.launcher3", "isSelected": false, "text": "Phone", "isFocusable": true, "isPassword": false, "centerX": 945, "isClickable": true, "isChecked": false, "isFocused": false, "isEnabled": true, "className": "android.widget.TextView", "isVisibleToUser": true }, { "isScrollable": false, "centerX": 135, "index": 12, "uuid": "dec9c272-397c-4395-8985-e2e583d5a567", "isLongClickable": true, "resourceId": "com.android.launcher3:id/icon", "isCheckable": false, "childCount": 0, "packageName": "com.android.launcher3", "isSelected": false, "isFocusable": true, "isPassword": false, "centerY": 1521, "isClickable": true, "text": "Play Store", "bounds": { "bottom": 1701, "right": 270, "left": 0, "top": 1341 }, "isChecked": false, "isFocused": false, "isEnabled": true, "className": "android.widget.TextView", "contentDescription": "Play Store", "isVisibleToUser": true }, { "isScrollable": false, "contentDescription": "Search", "index": 13, "isLongClickable": true, "resourceId": "com.android.launcher3:id/icon", "isCheckable": false, "bounds": { "bottom": 1701, "right": 540, "top": 1341, "left": 270 }, "childCount": 0, "text": "Search", "packageName": "com.android.launcher3", "isSelected": false, "centerX": 405, "isFocusable": true, "isPassword": false, "centerY": 1521, "isClickable": true, "isChecked": false, "isFocused": false, "isEnabled": true, "className": "android.widget.TextView", "isVisibleToUser": true, "uuid": "5c96c836-ea08-49a8-809b-10e7efb218de" }, { "isScrollable": false, "uuid": "aaf1f6f6-109f-4b28-b0f4-1206f2fbeabc", "text": "Settings", "centerX": 675, "isLongClickable": true, "index": 14, "resourceId": "com.android.launcher3:id/icon", "isCheckable": false, "childCount": 0, "contentDescription": "Settings", "packageName": "com.android.launcher3", "isSelected": false, "isFocusable": true, "isPassword": false, "centerY": 1521, "isClickable": true, "bounds": { "right": 810, "bottom": 1701, "top": 1341, "left": 540 }, "isChecked": false, "isFocused": false, "isEnabled": true, "className": "android.widget.TextView", "isVisibleToUser": true } ]

<br>

1. On the APP list page of the Android system, you can output the value of the 2nd DOM element in the list of elements matching the condition via the Find Element node. The element can be clicked via the Tap Element node.

    #### Configuration:

    | Field Name                                               | Field Value                                    |
    | -------------------------------------------------------- | ---------------------------------------------- |
    | **When Condition is Met**                                | "fullID Equals "com.android.launcher3:id/icon" |
    | **When there are multiple matching objects on the page** | "Get single element"                           |
    | **Which element to select?**                             | "2"                                            |
    | **Timeout for waiting for element to appear**            | "3000"                                         |
    | **Delay After Finding Element**                          | "0"                                            |

    #### Output:

    ##### Output Parameters

    "**Element**" is an element object (JSON) with the value:

    <details>
    <summary>Click to expand/collapse</summary>
    { "isScrollable": false, "text": "Chrome", "bounds": { "top": 261, "right": 540, "bottom": 621, "left": 270 }, "isLongClickable": true, "resourceId": "com.android.launcher3:id/icon", "index": 1, "isCheckable": false, "childCount": 0, "contentDescription": "Chrome", "packageName": "com.android.launcher3", "isSelected": false, "centerX": 405, "isFocusable": true, "isPassword": false, "isClickable": true, "isChecked": false, "isFocused": false, "isEnabled": true, "className": "android.widget.TextView", "centerY": 441, "isVisibleToUser": true, "uuid": "4aa1242a-daa8-46dd-8bf4-f100f3cf228a" }

    You can see the contentDescription value is "Chrome". In the next step, you can click this element via the [Tap Element](../01%20Simulation%20Operations/04%20Tap%20Element.md) node.
    
## Related Nodes

- [Tap Element](../01%20Simulation%20Operations/04%20Tap%20Element.md)
- [Run JS Script](../02%20Data%20Processing/01%20Run%20JS%20Script.md)



