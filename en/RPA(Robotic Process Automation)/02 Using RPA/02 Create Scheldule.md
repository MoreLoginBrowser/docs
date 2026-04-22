---
title: 02 Create Scheldule
tags:
  - Document
  - Tutorial
  - Using RPA
description: >-
  Once a template is created, you can create a scheldule to trigger it according
  to a schedule.
---

# Create Scheldule

Once a template is created, you can create a scheldule to trigger it according to a schedule.

## Step 1: Click Create Scheldule

You can create a scheldule in two ways:

1.  Create a scheldule via **Custom Template**.
2.  Create a scheldule via **Marketplace**.

Click the "Create Scheldule" button to start.


## Step 2: Fill in Scheldule Details

There are 3 steps in creating a scheldule. Click "Next" in the bottom left corner to proceed.

1.  **[Select Template]**
    1.  The selected template and its information in the left area do not need to be filled in.
        > [!NOTE]
        > Marketplace will include a detailed description and requirements for the App, version, and language.
    2.  Fill in the right area:
        1.  "Schedule Title" (Required)
        2.  "Description(Optional)"

2.  **[Select ＆ Configure]**
    1.  Select the "Cloud Phone" for the task in the left area.
    2.  Fill in configuration information required for the current template in the right area.

    > [!NOTE]
    > - Required parameters for each execution phone on the right must be filled in.
    > - A green checkmark will appear after parameters are filled for a phone. A gray number indicates incomplete information.

3.  **[Configure Execution Time]**
    1.  Select "Run Mode":
        1.  "Run Once": The task ends after a single execution.
        2.  "Run Daily": Executes a recurring task, triggered at a fixed time every day.
    2.  Set "Time":
        1.  Set the run time for each phone in the right area.
        2.  Recurring tasks will preview the next 3 run times on the right.

        > [!NOTE]
        > Monthly compiled cloud phones can run simultaneously. Minutely billed cloud phones allow a maximum of 5 to run simultaneously. If more than 5 cloud phones are executing RPA tasks at the same time, subsequent plans will wait for the preceding phones to finish before executing.

    3.  "End Date": Only for recurring tasks, such as "Run Daily".
    4.  "Time Zone": Defaults to the computer system's time zone.

## Next Steps

- How to view plan history tasks
- Edit scheldule

[View History Tasks](https://www.notion.so/2f185c1ea55a80268454fe8832a39532?pvs=21)

[Plan Operations](https://www.notion.so/2f185c1ea55a80fbac4fe0e705d9ec93?pvs=21)
