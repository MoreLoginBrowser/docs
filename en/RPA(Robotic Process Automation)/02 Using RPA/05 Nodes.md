---
title: 05 Nodes
tags:
  - Document
  - Tutorial
  - Using RPA
description: >-
  Nodes are an important capability in RPA. Through nodes, RPA can orderly
  complete a complex task. The following chapters will introduce the core
  nodes...
---

# Nodes

Nodes are an important capability in RPA. Through nodes, RPA can orderly complete a complex task. The following chapters will introduce the core nodes in MoreLogin in detail.

## Node Operations

- Click "..." on the node card to copy or delete the node.
- Click the card to expand the node configuration dialog.
- **Node Naming**: The title of the node at the top of the expanded dialog is editable, which is very specific for distinguishing multiple nodes in complex workflows.
- After the node runs successfully, you can click "View Logs" on the right.

## "Configuration" and "Output" in Node Dialog

Each node contains configuration and output.

- **Configuration**: Contains information driving the current node, similar to function parameter input in programming.
- **Output**: Information output from executing the current node. Output generally includes two parts: return parameters and execution log.
    - "Output Parameters": Parameters returned by the current node. You can reference current return parameters in subsequent nodes (e.g., extracting text from an element).
    - "Execution Log": Execution results of the current node, facilitating the view of historical tasks or node run status when testing templates.
        - Start Time
        - End Time
        - Duration (ms)
        - Status (Success/Failure)

## Variable Referencing

Variable referencing is an important feature in MoreLogin RPA. Variables generated in the process are automatically saved in the "Output" of each node. You can reference them at any time via the "+" after the input box in subsequent steps.


## Node Run Status

When the workflow finishes running, each node will display its current run status.

- The leftmost side of the card shows the execution status:
    - "Success": ☑️
    - "Failure": X
    - "Running": loading
    - "Not Run": None
- Click the "Output" button in the card or select the "Output" Tab to view the node's run output info, facilitating the check of each step's run status in the template.

## Node Introduction

Nodes in MoreLogin can be divided into the following categories. You can add a new node by clicking "+" between two adjacent nodes in the workflow.


1.  **Simulation Operations**
    - [Launch APP](../03-node/01-simulation-operations/01-launch-app.md)
    - [Close APP](../03-node/01-simulation-operations/02-close-app.md)
    - [Tap Element](../03-node/01-simulation-operations/04-tap-element.md)
    - [Find Element](../03-node/01-simulation-operations/03-find-element.md)
    - [Tap(x,y)](../03-node/01-simulation-operations/05-tap-x-y.md)
    - [Click via text recognition (OCR)](../03-node/01-simulation-operations/06-click-via-ocr.md)
    - [Swipe Page](../03-node/01-simulation-operations/07-swipe-page.md)
    - [Input Text](../03-node/01-simulation-operations/08-input-text.md)
    - [Keyboard Actions](../03-node/01-simulation-operations/09-keyboard-actions.md)
    - [Press Key](../03-node/01-simulation-operations/10-press-key.md)
    - [Run ADB Shell](../03-node/01-simulation-operations/11-run-adb-shell.md)

2.  **Data Processing**
    - [Run JS Script](../03-node/02-data-processing/01-run-js-script.md)

3.  **Flow Logic**
    - [Wait](../03-node/03-flow-logic/01-wait.md)
    - [Loop](../03-node/03-flow-logic/02-loop.md)
    - [Switch](../03-node/03-flow-logic/03-switch.md)

4.  **Files**
    - [Mobile File Management](../03-node/04-file-management/01-mobile-file-management.md)
    - [Download File to Phone](../03-node/04-file-management/02-download-file-to-phone.md)

5.  **Tools**
    - [HTTP Request](../03-node/05-tools/01-http-request.md)

[Initial Settings](../03-node/00-initialization/00-initialization.md)
