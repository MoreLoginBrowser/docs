---
title: 03 Find Element
tags:
  - Document
  - Tutorial
  - Simulation Operations
description: 'You can do the following with the current node:'
---

# Find Element 

You can do the following with the current node:
1. Find view tree elements on the current page, then click the element via the [Tap Element](../01%20Simulation%20Operations/04%20Tap%20Element.md) node
2. Find specific view tree elements, then get the element's attributes via the [Run JS Script](../02%20Data%20Processing/01%20Run%20JS%20Script.md) node
3. Find specific view tree elements, then check if the element exists via the current node's output, similar to printing logs in print debugging

[What is a view tree?](../../05%20附录/02%20What%20is%20a%20view%20tree%3F.md)

## Parameters

- **Selector Type** Dropdown
    - By Find Element
    - Use Previous Element

If "By Find Element" is selected, you can filter elements through the following DOM node conditions. Elements matching the attribute conditions you set will be filtered out by the executor.

- You can add required conditions in **[When Condition is Met]**. Supports the following 4 conditions, with up to 4 parallel filters supported simultaneously:
    - text
    - fullId
    - class
    - desc

    You can get the element attributes of the current cloud phone screen via the developer tools.


- **[When there are multiple matching objects on the page]**

    - Get single element
      - **[Which element to select?]**
        - When "Get Single element" is selected, this option appears. You can enter the corresponding index number, for example, entering number 1 means you will get the 1st matching element
    - Get element list


"Use Previous Element": Directly matches the DOM node of the element in actual execution. This function is often used with the "Find Element" node.

- **Maximum Wait Time for Element to Appear**
    - After filling in the number, the current finder will poll for the element you need to find. Execution continues after the element is found. If the element is not found within this time, the next node begins execution.
    - Can fill in or reference a number, unit is milliseconds.

- **[Delay After Finding Element]**

## Output

- **Output Parameters**
    - Element: Output in node format (actually JSON). You can parse the content in the element directly by executing "Run JS Script".


- **Execution Log**
    - Start Time
    - End Time
    - Duration (ms)
    - Status (Success/Failure)

## Example

1. On the APP list page of the Android system, you can output the DOM element of each APP via the Find Element node. In the next step, you can iterate through the DOM element of each APP via the Loop node, and then check the name of each APP via the Run JS Script node.

    #### Configuration:

    | Field Name                                               | Field Value                                     |
    | -------------------------------------------------------- | ----------------------------------------------- |
    | **When Condition is Met**                                | "fullID" Equals "com.android.launcher3:id/icon" |
    | **When there are multiple matching objects on the page** | Get element list                                |
    | **Timeout for waiting for element to appear**            | 3000                                            |
    | **Delay After Finding Element**                          | 0                                               |

    #### Output:

    ##### Output Parameters

    "**Element list**" is a list with the value:

    <details>
    <summary>Click to expand/collapse</summary>
    [ { "isScrollable": false, "centerX": 135, "uuid": "1b03ee9a-91bd-457f-9981-7f2bfba0905b", "isLongClickable": true, "resourceId": "com.android.launcher3:id/icon", "index": 0, "isCheckable": false, "childCount": 0, "bounds": { "top": 261, "right": 270, "left": 0, "bottom": 621 }, "packageName": "com.android.launcher3", "isSelected": false, "isFocusable": true, "isPassword": false, "contentDescription": "Calendar", "isClickable": true, "isChecked": false, "isFocused": false, "isEnabled": true, "className": "android.widget.TextView", "centerY": 441, "text": "Calendar", "isVisibleToUser": true }, { "isScrollable": false, "text": "Chrome", "isLongClickable": true, "resourceId": "com.android.launcher3:id/icon", "index": 1, "isCheckable": false, "uuid": "6446a15a-47e9-4ee3-adcd-8f63197653d4", "childCount": 0, "contentDescription": "Chrome", "packageName": "com.android.launcher3", "isSelected": false, "bounds": { "top": 261, "right": 540, "bottom": 621, "left": 270 }, "centerX": 405, "isFocusable": true, "isPassword": false, "isClickable": true, "isChecked": false, "isFocused": false, "isEnabled": true, "className": "android.widget.TextView", "centerY": 441, "isVisibleToUser": true }, { "isScrollable": false, "centerX": 675, "isLongClickable": true, "resourceId": "com.android.launcher3:id/icon", "uuid": "d5ae8607-be23-4166-a332-32911dc5eae0", "isCheckable": false, "childCount": 0, "index": 2, "packageName": "com.android.launcher3", "isSelected": false, "isFocusable": true, "isPassword": false, "isClickable": true, "text": "Clock", "isChecked": false, "isFocused": false, "isEnabled": true, "className": "android.widget.TextView", "contentDescription": "Clock", "centerY": 441, "bounds": { "right": 810, "top": 261, "left": 540, "bottom": 621 }, "isVisibleToUser": true }, { "isScrollable": false, "contentDescription": "Contacts", "isLongClickable": true, "resourceId": "com.android.launcher3:id/icon", "isCheckable": false, "index": 3, "childCount": 0, "packageName": "com.android.launcher3", "isSelected": false, "text": "Contacts", "isFocusable": true, "isPassword": false, "centerX": 945, "uuid": "6f920c6c-221c-425c-b5b1-d438b1fc7fe9", "isClickable": true, "isChecked": false, "isFocused": false, "isEnabled": true, "className": "android.widget.TextView", "centerY": 441, "bounds": { "top": 261, "right": 1080, "bottom": 621, "left": 810 }, "isVisibleToUser": true }, { "isScrollable": false, "centerX": 135, "centerY": 801, "bounds": { "bottom": 981, "right": 270, "left": 0, "top": 621 }, "isLongClickable": true, "text": "Files", "resourceId": "com.android.launcher3:id/icon", "contentDescription": "Files", "isCheckable": false, "childCount": 0, "packageName": "com.android.launcher3", "index": 4, "isSelected": false, "isFocusable": true, "isPassword": false, "isClickable": true, "isChecked": false, "isFocused": false, "isEnabled": true, "className": "android.widget.TextView", "uuid": "3e8b09e7-4948-4132-9ca8-0ca57cf5a12d", "isVisibleToUser": true }, { "isScrollable": false, "contentDescription": "Gallery", "centerY": 801, "isLongClickable": true, "resourceId": "com.android.launcher3:id/icon", "isCheckable": false, "childCount": 0, "index": 5, "text": "Gallery", "packageName": "com.android.launcher3", "isSelected": false, "centerX": 405, "isFocusable": true, "isPassword": false, "isClickable": true, "isChecked": false, "isFocused": false, "isEnabled": true, "className": "android.widget.TextView", "uuid": "7b1b7b09-3ca0-422d-b35a-37ce26e2517b", "isVisibleToUser": true, "bounds": { "bottom": 981, "right": 540, "top": 621, "left": 270 } }, { "isScrollable": false, "centerY": 801, "centerX": 675, "isLongClickable": true, "resourceId": "com.android.launcher3:id/icon", "isCheckable": false, "childCount": 0, "packageName": "com.android.launcher3", "isSelected": false, "bounds": { "right": 810, "bottom": 981, "top": 621, "left": 540 }, "index": 6, "contentDescription": "Gmail", "uuid": "9b8815b9-1079-4969-bf77-c3b27e4656f0", "isFocusable": true, "isPassword": false, "isClickable": true, "isChecked": false, "isFocused": false, "isEnabled": true, "className": "android.widget.TextView", "isVisibleToUser": true, "text": "Gmail" }, { "isScrollable": false, "text": "Instagram", "centerY": 801, "uuid": "045888d5-9154-4a2a-b6da-649f6c54e9da", "isLongClickable": true, "resourceId": "com.android.launcher3:id/icon", "bounds": { "bottom": 981, "right": 1080, "top": 621, "left": 810 }, "isCheckable": false, "childCount": 0, "contentDescription": "Instagram", "packageName": "com.android.launcher3", "isSelected": false, "index": 7, "isFocusable": true, "isPassword": false, "centerX": 945, "isClickable": true, "isChecked": false, "isFocused": false, "isEnabled": true, "className": "android.widget.TextView", "isVisibleToUser": true }, { "isScrollable": false, "index": 8, "uuid": "4ad6d1e9-02a4-4163-968b-b764968a2e1b", "centerX": 135, "text": "Messaging", "isLongClickable": true, "bounds": { "top": 981, "right": 270, "left": 0, "bottom": 1341 }, "resourceId": "com.android.launcher3:id/icon", "isCheckable": false, "childCount": 0, "centerY": 1161, "contentDescription": "Messaging", "packageName": "com.android.launcher3", "isSelected": false, "isFocusable": true, "isPassword": false, "isClickable": true, "isChecked": false, "isFocused": false, "isEnabled": true, "className": "android.widget.TextView", "isVisibleToUser": true }, { "isScrollable": false, "index": 9, "text": "PhoneGrid Bot", "isLongClickable": true, "resourceId": "com.android.launcher3:id/icon", "isCheckable": false, "childCount": 0, "centerY": 1161, "packageName": "com.android.launcher3", "isSelected": false, "contentDescription": "PhoneGrid Bot", "centerX": 405, "isFocusable": true, "isPassword": false, "isClickable": true, "uuid": "fa990303-fa24-4c27-bc1b-32dec1d15fc7", "bounds": { "top": 981, "right": 540, "bottom": 1341, "left": 270 }, "isChecked": false, "isFocused": false, "isEnabled": true, "className": "android.widget.TextView", "isVisibleToUser": true }, { "isScrollable": false, "index": 10, "bounds": { "right": 810, "top": 981, "left": 540, "bottom": 1341 }, "centerX": 675, "isLongClickable": true, "resourceId": "com.android.launcher3:id/icon", "isCheckable": false, "childCount": 0, "centerY": 1161, "packageName": "com.android.launcher3", "isSelected": false, "isFocusable": true, "isPassword": false, "isClickable": true, "contentDescription": "Open Camera", "isChecked": false, "isFocused": false, "isEnabled": true, "className": "android.widget.TextView", "text": "Open Camera", "uuid": "55fd0ae2-cb1b-44f9-93af-91064aaebea2", "isVisibleToUser": true }, { "isScrollable": false, "index": 11, "contentDescription": "Phone", "bounds": { "top": 981, "right": 1080, "bottom": 1341, "left": 810 }, "isLongClickable": true, "resourceId": "com.android.launcher3:id/icon", "uuid": "355737cc-e262-4c9a-872a-79ce9ff01bdd", "isCheckable": false, "childCount": 0, "centerY": 1161, "packageName": "com.android.launcher3", "isSelected": false, "text": "Phone", "isFocusable": true, "isPassword": false, "centerX": 945, "isClickable": true, "isChecked": false, "isFocused": false, "isEnabled": true, "className": "android.widget.TextView", "isVisibleToUser": true }, { "isScrollable": false, "centerX": 135, "index": 12, "uuid": "dec9c272-397c-4395-8985-e2e583d5a567", "isLongClickable": true, "resourceId": "com.android.launcher3:id/icon", "isCheckable": false, "childCount": 0, "packageName": "com.android.launcher3", "isSelected": false, "isFocusable": true, "isPassword": false, "centerY": 1521, "isClickable": true, "text": "Play Store", "bounds": { "bottom": 1701, "right": 270, "left": 0, "top": 1341 }, "isChecked": false, "isFocused": false, "isEnabled": true, "className": "android.widget.TextView", "contentDescription": "Play Store", "isVisibleToUser": true }, { "isScrollable": false, "contentDescription": "Search", "index": 13, "isLongClickable": true, "resourceId": "com.android.launcher3:id/icon", "isCheckable": false, "bounds": { "bottom": 1701, "right": 540, "top": 1341, "left": 270 }, "childCount": 0, "text": "Search", "packageName": "com.android.launcher3", "isSelected": false, "centerX": 405, "isFocusable": true, "isPassword": false, "centerY": 1521, "isClickable": true, "isChecked": false, "isFocused": false, "isEnabled": true, "className": "android.widget.TextView", "isVisibleToUser": true, "uuid": "5c96c836-ea08-49a8-809b-10e7efb218de" }, { "isScrollable": false, "uuid": "aaf1f6f6-109f-4b28-b0f4-1206f2fbeabc", "text": "Settings", "centerX": 675, "isLongClickable": true, "index": 14, "resourceId": "com.android.launcher3:id/icon", "isCheckable": false, "childCount": 0, "contentDescription": "Settings", "packageName": "com.android.launcher3", "isSelected": false, "isFocusable": true, "isPassword": false, "centerY": 1521, "isClickable": true, "bounds": { "right": 810, "bottom": 1701, "top": 1341, "left": 540 }, "isChecked": false, "isFocused": false, "isEnabled": true, "className": "android.widget.TextView", "isVisibleToUser": true } ]

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



