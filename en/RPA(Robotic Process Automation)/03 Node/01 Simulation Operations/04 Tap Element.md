---
title: 04 Tap Element
tags:
  - Document
  - Tutorial
  - Simulation Operations
description: 'RPA provides 3 ways to simulate clicking:'
---

# Tap Element

RPA provides 3 ways to simulate clicking:

1.  [Tap Element](../01%20Simulation%20Operations/04%20Tap%20Element.md): Locate and click the current element through the DOM elements of the UI tree.
2.  [Tap(x, y)](../01%20Simulation%20Operations/05%20Tap(x,%20y).md): Locate the click position through the X and Y axis coordinates of the current screen.
3.  [Click via text recognition (OCR)](../01%20Simulation%20Operations/06%20Click%20via%20OCR.md): Click by recognizing the text position on the current screen.

The following details the function of Tap Element.

## Parameters

- **[Select Type]** Dropdown
    - By Find Element
    - Use Previous Element

If "By Find Element" is selected, you can filter elements through the following DOM node conditions. Elements matching the attribute conditions you set will be filtered out by the executor.

- You can add required conditions in **[When Condition is Met]**. Supports the following 4 conditions, with up to 4 parallel filters supported simultaneously:
    - text
    - fullId
    - class
    - desc

    You can get the element attributes of the current cloud phone screen via the [developer tools](../../02%20Using%20RPA/04%20Developer%20Tools.md).

If you have already selected an element through a previous node, you can select **[Use Previous Element]**.

**QA: Difference between "By Find Element" and "Use Previous Element"?**

"By Find Element": Filters to find elements matching conditions.

"Use Previous Element": Directly matches the DOM node of the element in actual execution. This function is often used with the "Find Element" node.

- **[Maximum Wait Time for Element to Appear]**
    - After filling in the number, the current finder will poll for the element you need to find. Execution continues after the element is found. If the element is not found within this time, the next node begins execution.
    - Can fill in or reference a number, unit is milliseconds.

- **[Tap Type]**
    - Single Tap
    - Double Tap
    - Long Press
        - When Long Press is selected, you can set **[Press Duration]** in milliseconds.

- **[Delay After Tap]**

## Output

- **Output Parameters**
    - Element: Output in node format (actually JSON). You can parse the content in the element directly by executing "Run JS Script".

- **Execution Log**
    - Start Time
    - End Time
    - Duration (ms)
    - Status (Success/Failure)

## Example

For example, on the cloud phone desktop, there is a Google Play Store. I want to find and click this area via element lookup. Parameters are as follows:

| Field Name                | Field Value                |
| ------------------------- | -------------------------- |
| **Select Type**           | By Find Element            |
| **When Condition is Met** | "text" Equals "Play Store" |
| **Input Field Timeout**   | 3000                       |
| **Tap Type**              | Single Tap                 |
| **Delay After Tap**       | 0                          |

## Related Nodes

[Find Element](../01%20Simulation%20Operations/03%20Find%20Element.md)
