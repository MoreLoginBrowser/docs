---
title: 06 Click via OCR
tags:
  - Document
  - Tutorial
  - Simulation Operations
description: 'RPA provides 3 ways to simulate clicking:'
---

# Click via text recognition (OCR)

RPA provides 3 ways to simulate clicking:

1.  [Tap Element](../01%20Simulation%20Operations/04%20Tap%20Element.md): Locate and click the current element through the DOM elements of the UI tree.
2.  [Tap(x, y)](../01%20Simulation%20Operations/05%20Tap(x,%20y).md): Locate the click position through the X and Y axis coordinates of the current screen.
3.  [Click via text recognition (OCR)](../01%20Simulation%20Operations/06%20Click%20via%20OCR.md): Click by recognizing the text position on the current screen.


The following details the function of Click via text recognition (OCR).

## Parameters

- **Enter matching text**
    - You can input text on the screen.
- **When there are multiple matching objects on the page**
    - Get single element
    - Get element list
- **Click after matching the object**
    - On: Click after finding the element
    - Off: Only find the element
- **Click position**
    - Center Point
    - Random point within the matched object area
    - Custom
        - Offset from the center point
            - You can adjust the click position by the offset value from the element center point.
- **Tap Type**
    - Single Tap
    - Double Tap
    - Long Press
- **Delay After Finding Element**

## Output

### Output Parameters

> Text area: { "height": 30, "left": 343, "width": 142, "top": 332, "centerY": 347, "centerX": 414, "bottom": 362, "right": 485 }

#### Output Field Explanation

| key     | Explanation                                        |
| :------ | :------------------------------------------------- |
| height  | Height of the element                              |
| width   | Width of the element                               |
| top     | Y-axis coordinate of the top of the element        |
| left    | X-axis coordinate of the left side of the element  |
| bottom  | Y-axis coordinate of the bottom of the element     |
| right   | X-axis coordinate of the right side of the element |
| centerY | Y-axis coordinate of the center of the element     |
| centerX | X-axis coordinate of the center of the element     |

### Execution Log

- Start Time
- End Time
- Duration (ms)
- Status (Success/Failure)

## Example

For example, on the cloud phone desktop, hope to click Chrome browser.

### Configuration is as follows:

- **Enter matching text**: "Chrome"
- **When there are multiple matching objects on the page**: "Get single element"
- **Click after matching the object**: "On"
- **Click position**: "Center Point"
- **Tap Type**: "Single Tap"
- **Delay After Finding Element**: "0"

### "Output Parameters" in Output:

> Text area: { "height": 30, "left": 343, "width": 142, "top": 332, "centerY": 347, "centerX": 414, "bottom": 362, "right": 485 }

## Related Nodes

Tap Element

Run JS Script
