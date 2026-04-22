---
title: 08 Input Text
tags:
  - Document
  - Tutorial
  - Simulation Operations
description: '- [Input Selector Type] Dropdown'
---

# Input Text

## Parameters

- **[Input Selector Type]** Dropdown
    - By Find Element
    - Use Previous Element

- You can add required conditions in **[When Condition is Met]**. Supports the following 4 conditions, with up to 4 parallel filters supported simultaneously:
    - text
    - fullId
    - class
    - desc

    You can get the element attributes of the current cloud phone screen via the developer tools.

- **[Input Field Timeout]** (Number)
    - After filling in the number, the current finder will poll for the element you need to find. Execution continues after the element is found. If the element is not found within this time, the next node begins execution.
    - Can fill in or reference a number, unit is milliseconds.

- **[Input Text]** (String)
    - Input text character limit is 2000 characters.

- **[Clear Field Before Typing]** Switch
    - On: Clears the content of the input box before inputting text (Default).
    - Off: If there is content in the input box, the currently input text will be appended to the original content.

- **[Press Enter After Input]** Switch
    - On: Clicks Enter after inputting text.
    - Off: Ends after inputting text (Default).

- **[Delay After Input]**(Number)

## Output

- **Output Parameters**
    - Element: Output as a positioning node. You can reference this node or parse this node content (JSON) in the subsequent process. You can judge whether the positioning is correct through the input node information.


- **Execution Log**
    - Start Time
    - End Time
    - Duration (ms)
    - Status (Success/Failure)

## Example

For example, on the cloud phone desktop, hope to input "morelogin antidetect browser" in the Google search box. Find the fullID of the search box via developer tools as "com.android.quicksearchbox:id/search_src_text".

Configuration is as follows:

| key                             | Explanation                                                     |
| :------------------------------ | :-------------------------------------------------------------- |
| **Select Type**                 | By Find Element                                                 |
| **When Condition is Met**       | "fullId" Equals "com.android.quicksearchbox:id/search_src_text" |
| **Input Field Timeout**         | 3000                                                            |
| **Input Content**               | morelogin antidetect browser                                    |
| **Clear Field Before Typing**   | On                                                              |
| **Press Enter After Input**     | Off                                                             |
| **Delay After Finding Element** | 0                                                               |

"Output Parameters" in Output:

Element: { "isScrollable": false, "centerY": 35, "resourceId": "com.android.systemui:id/clock", "centerX": 71, [To be completed]

## Related Nodes

[Find Element](../01%20Simulation%20Operations/03%20Find%20Element.md)

[Tap Element](../01%20Simulation%20Operations/04%20Tap%20Element.md)

[Run JS Script](../02%20Data%20Processing/01%20Run%20JS%20Script.md)
