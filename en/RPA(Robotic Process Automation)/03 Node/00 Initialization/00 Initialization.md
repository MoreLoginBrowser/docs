---
title: 00 Initialization
tags:
  - Document
  - Tutorial
  - Initialization
description: >-
  After configuring a template, if you need to run it repeatedly, you can
  configure your variables in the initial settings. This facilitates
  configuring...
---

# Initial Settings

## Introduction

After configuring a template, if you need to run it repeatedly, you can configure your variables in the initial settings. This facilitates configuring the variables you need to fill in when executing the task later.

The content filled in the initial settings will not be saved to the template. The template only saves the field configuration.

## How to use?

Click "Initial Settings" in the bottom left corner of the template editor or click the first step "Initial Settings" node to open the initialization template. You can add variables you need to use in the current template in the initial settings.

### Example:

For example, if my current template is a X/Twitter posting workflow, I need to input different content every time I use this template.

**Step 1: Add initialization field "Post content" in the template**

In the template editing page, click "Initial Settings" in the bottom left corner to open the initialization dialog.

Click "Create Intialization Form", add a field, and select "Text".

The added field configuration is as follows:

- **Title Content**: "Post Content"
- **Input placeholder Text**: "Enter your x post content"
- **Required**: On
- **Multi-line input**: On
- **Input Character Limit**: Off
- **Enter Default Text**: Off (You can turn this on if there is a default variable)

Click "Save" after filling in the form.


**Step 2: Complete your template and reference in relevant nodes**

In the "Input Text" node, you can click the "+" on the right side of the input box to reference the initialized variable.

You can see the reference to "Initialization Parameters" added in the first step of initialization parameters here.


Finally, after your template is saved, it is convenient for you to quickly fill in the initialized variables and execute.

**Method 1. Single Run**

Open the template, click "Test" in the bottom left corner. You can fill in "Post Content" to quickly test run the current template.

**Method 2. Create Scheldule**

You can fill in the initialized variables in Step 2 of creating a plan.

**Method 3. Call template via API**

You can fill in the variable content in **Creating a once schedule**.

## Supported Fields

- Text
- Decimal
- Number
- Image
- Video
- Boolean

## Related Nodes

[Input Text](../01%20Simulation%20Operations/08%20Input%20Text.md)
