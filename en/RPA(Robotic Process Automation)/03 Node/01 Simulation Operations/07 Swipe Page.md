---
title: 07 Swipe Page
tags:
  - Document
  - Tutorial
  - Simulation Operations
description: '- [Swipe Start Coordinates]'
---

# Swipe Page

## Parameters

- **[Swipe Start Coordinates]**
    - X (Number)
    - Y (Number)

    You can get X and Y coordinate values in the cloud phone via the developer tools.

- **[Swipe End Coordinates]**
    - X (Number)
    - Y (Number)

    You can get X and Y coordinate values in the cloud phone via the developer tools.

- **[Coordinate Random Offset]** (Number)

    Default is 0. When an offset value is set, the start and end positions will be randomly offset up, down, left, or right within the offset range each time.

    For example, if X: 50, Y: 100 is set, and the random coordinate offset is 10, then the range for X is 40px–60px, and the range for Y is 90px–110px.

- **[Swipe Duration]**
    - Duration of the swipe from start point to end point, in milliseconds.

- **[Delay After Swipe]**

## Output

- **Output Parameters**
    - None
- **Execution Log**
    - Start Time
    - End Time
    - Duration (ms)
    - Status (Success/Failure)

## Example

For example, on the cloud phone desktop, swipe up to the APP drawer. Find the start and end positions via developer tools (Start X: 270, Y: 1500; End X: 270, Y: 1150). Parameters are as follows:


- **Swipe Start Coordinates**
    - X: "270"
    - Y: "1500"
- **Swipe End Coordinates**
    - X: "270"
    - Y: "1150"
- **Coordinate Random Offset**: "0"
- **Delay After Swipe**: "0"

## Related Nodes

[Tap(x, y)](../01%20Simulation%20Operations/05%20Tap(x,%20y).md)
