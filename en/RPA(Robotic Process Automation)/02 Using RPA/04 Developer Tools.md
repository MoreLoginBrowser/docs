---
title: 04 Developer Tools
tags:
  - Document
  - Tutorial
  - Using RPA
description: >-
  We provide developer tools to help users grab the Cloud Phone View Tree. You
  can connect to our cloud phone and easily obtain the structure and conten...
---

# Developer Tools

We provide developer tools to help users grab the Cloud Phone View Tree. You can connect to our cloud phone and easily obtain the structure and content of the View Tree. Some necessary information used in important nodes when editing templates relies on element properties from the debuggerging tool.

## Step 1: Select Cloud Phone in Edit Template

When creating or modifying a template, click "Select Cloud Phone" in the upper right corner.

## Step 2: Open Cloud Phone Debugger

1.  After selecting a cloud phone, open the current cloud phone in the upper right corner.
2.  After the cloud phone boots up, click the <img src="../image/debug_icon.png" style="width:30px; height:30px; vertical-align: middle; margin:0 2px;" /> button to enter Debugger.

<img src="../image/enter_debug.png" style="width:1400px; height:400px; vertical-align: middle; margin:0 2px; border: 1px solid #D9D9D9;"/>

<br>

<img src="../image/phone_debug.png" style="width:1400px; height:400px; vertical-align: middle; margin:0 2px; border: 1px solid #D9D9D9;"/>

## How to use Debugger?

1.  **Snapshot Mode**
    1.  Click "Create Snapshot", and the debugger tool will save the UI tree of the current cloud phone page.
    2.  In snapshot mode, hovering over the cloud phone screen on the left will show a red box, and the UI tree on the right will highlight the corresponding DOM element.
    3.  In snapshot mode, the page is not clickable for interaction, and the virtual buttons below are also disabled.

2.  **Close Snapshot Mode**
    1.  Click the "Snapshot Mode" switch in the upper right of the debugger tool to close snapshot mode.
    2.  After closing snapshot mode, the phone and virtual buttons resume working.

## Element Property Description

- **X**: Center point position of the element on the X-axis.
- **Y**: Center point position of the element on the Y-axis.
- **bounds**: Coordinates of the top-left and bottom-right corners of the element, e.g., `[789,96][1038,404]`.
    - Related Node: [Tap(x, y)](../03%20Node/01%20Simulation%20Operations/05%20Tap(x,%20y).md)
- **text**: Visible text content on the control, usually text the user can see directly.
- **fullID**: In Android development, developers set IDs like `android:id="@+id/btn_submit"`. fullID is the complete form including the package name (e.g., `com.example.app:id/btn_submit`).
- **class**: The Android system class name of the control, representing the "type" of the control (e.g., button, text box, list, etc.).
- **desc**: Description text of the control, also called "content description", mainly used for accessibility (e.g., screen readers).
    - Related Nodes: [Find Element](../03%20Node/01%20Simulation%20Operations/03%20Find%20Element.md), [Tap Element](../03%20Node/01%20Simulation%20Operations/04%20Tap%20Element.md)
- **package**: A unique identifier assigned by the Android system to each application, usually in the format of "reverse domain + app identifier" (e.g., `com.taobao.taobao`, `com.tencent.mm`). It is essentially the "ID card number" of every App in the Android device.
    - Related Node: [Launch APP](../03%20Node/01%20Simulation%20Operations/01%20Launch%20APP.md), [Close APP](../03%20Node/01%20Simulation%20Operations/02%20Close%20APP.md)
