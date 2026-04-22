---
title: 05 Nodes
tags:
  - Document
  - Tutorial
  - Using RPA
description: 节点是 RPA 中的一项重要能力。通过节点，RPA可以有序地完成复杂的任务。后续章节将详细介绍MoreLogin中的核心节点。
---
# 节点

节点是 RPA 中的一项重要能力。通过节点，RPA可以有序地完成复杂的任务。后续章节将详细介绍MoreLogin中的核心节点。

## 节点操作

- 单击节点卡上的“...”以复制或删除节点。
- 单击该卡可展开节点配置对话框。
- **节点命名**：展开对话框顶部的节点标题是可编辑的，这对于区分复杂工作流程中的多个节点非常具体。
- 节点运行成功后，可以点击右侧“查看日志”。

## 节点对话框中的“配置”和“输出”

每个节点包含配置和输出。

- **配置**：包含驱动当前节点的信息，类似于编程中的函数参数输入。
- **输出**：执行当前节点输出的信息。输出一般包括两部分：返回参数和执行日志。
    - “输出参数”：当前节点返回的参数。您可以在后续节点中引用当前返回参数（例如，从元素中提取文本）。
    - “执行日志”：当前节点的执行结果，方便测试模板时查看历史任务或节点运行状态。
        - 开始时间
        - 结束时间
        - 持续时间（毫秒）
        - 状态（成功/失败）

## 变量引用

变量引用是 MoreLogin RPA 的一个重要功能。过程中产生的变量会自动保存在每个节点的“Output”中。您可以在后续步骤中随时通过输入框后的“+”引用它们。


## 节点运行状态

当工作流运行完成后，每个节点都会显示其当前的运行状态。

- 卡片最左侧显示执行状态：
    - “成功”：☑️
    - “失败”：X
    - “运行”：加载
    - “不运行”：无
- 点击卡片中的“输出”按钮或选择“输出”选项卡，可以查看节点的运行输出信息，方便查看模板中各步骤的运行状态。

## 节点介绍

MoreLogin中的节点可以分为以下几类。您可以通过单击工作流中两个相邻节点之间的“+”来添加新节点。


1. **模拟操作**
    - [启动应用程序](../03-node/01-simulation-operations/01-launch-app.md)
    - [关闭APP](../03-node/01-simulation-operations/02-close-app.md)
    - [点击元素](../03-node/01-simulation-operations/04-tap-element.md)
    - [查找元素](../03-node/01-simulation-operations/03-find-element.md)
    - [点击(x,y)](../03-node/01-simulation-operations/05-tap-x-y.md)
    - [通过文本识别（OCR）点击](../03-node/01-simulation-operations/06-click-via-ocr.md)
    - [滑动页面](../03-node/01-simulation-operations/07-swipe-page.md)
    - [输入文本](../03-node/01-simulation-operations/08-input-text.md)
    - [键盘操作](../03-node/01-simulation-operations/09-keyboard-actions.md)
    - [按键](../03-node/01-simulation-operations/10-press-key.md)
    - [运行ADB Shell](../03-node/01-simulation-operations/11-run-adb-shell.md)

2. **数据处理**
    - [运行JS脚本](../03-node/02-data-processing/01-run-js-script.md)

3. **流程逻辑**
    - [等待](../03-node/03-flow-logic/01-wait.md)
    - [循环](../03-node/03-flow-logic/02-loop.md)
    - [开关](../03-node/03-flow-logic/03-switch.md)

4. **文件**
    - [移动文件管理](../03-node/04-file-management/01-mobile-file-management.md)
    - [下载文件到手机](../03-node/04-file-management/02-download-file-to-phone.md)

5. **工具**
    - [HTTP 请求](../03-node/05-tools/01-http-request.md)

[初始设置](../03-node/00-initialization/00-initialization.md)
