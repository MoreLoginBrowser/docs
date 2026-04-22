---
title: '05 Tap(x, y)'
tags:
  - Document
  - Tutorial
  - Simulation Operations
description: 'RPA provides 3 ways to simulate clicking:'
---

# Tap(x, y)

RPA provides 3 ways to simulate clicking:

1.  [Tap Element](../01%20Simulation%20Operations/04%20Tap%20Element.md): Locate and click the current element through the DOM elements of the UI tree.
2.  [Tap(x, y)](../01%20Simulation%20Operations/05%20Tap(x,%20y).md): Locate the click position through the X and Y axis coordinates of the current screen.
3.  [Click via text recognition (OCR)](../01%20Simulation%20Operations/06%20Click%20via%20OCR.md): Click by recognizing the text position on the current screen.


The following details the Tap(x, y) function.

## Parameters

- **[Coordinates]**
    - X (Number)
    - Y (Number)

    You can get X and Y coordinate values in the cloud phone via the [developer tools](../../02%20Using%20RPA/04%20Developer%20Tools.md).

- **[Coordinate Random Offset]** (Number)

    Default is 0. When an offset value is set, the click position will be randomly offset up, down, left, or right within the offset range each time.

    For example, if X: 50, Y: 100 is set, and the random coordinate offset is 10, then the range for X is 40px–60px, and the range for Y is 90px–110px.

- **[Tap Type]**
    - Single Tap
    - Double Tap
    - Long Press
        - When Long Press is selected, you can set **[Press Duration]** in milliseconds.

- **[Delay After Tap]**

## Output

- **Output Parameters**
    - None

- **Execution Log**
    - Start Time
    - End Time
    - Duration (ms)
    - Status (Success/Failure)

## Example

For example, on the cloud phone desktop, there is a Google Play Store. Through the developer tools, the center point coordinates are found to be (X: 927, Y: 1326). Parameters are as follows:

| key                          | Explanation         |
| :--------------------------- | :------------------ |
| **Coordinates**              | X: "927", Y: "1326" |
| **Coordinate Random Offset** | 0                   |
| **Tap Type**                 | Single Tap          |
| **Delay After Tap**          | 0                   |

## Related Nodes

[Swipe Page](../01%20Simulation%20Operations/07%20Swipe%20Page.md)
