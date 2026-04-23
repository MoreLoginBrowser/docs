---
title: Make
tags:
  - Document
  - Tutorial
  - Trigger PhoneGrid Template Externally
description: >-
  Great news! PhoneGrid is now natively supported on Make (formerly Integromat).
  This means you don't need to mess with complex API code—you can connect...
---
# [Tutorial] How to Automate PhoneGrid Cloud Phones with Make.com (Native App)

Great news! **PhoneGrid** is now natively supported on **Make (formerly Integromat)**. This means you don't need to mess with complex API code—you can connect your cloud phones and automation templates just like in Zapier, but with Make's powerful visual workflow builder.

Here is how to set up your first automation scenario.

## Prerequisites
* **Make Account**
* **PhoneGrid API ID & Key**
    * *(Get these from PhoneGrid Dashboard -> API Management)*
[How to get API ID and API KEY?](https://guide.phonegrid.com/api-reference/open-api#get-started-with-phonegrid-open-apis)
---

## Step 1: Add the PhoneGrid Module
1.  Log in to Make and click **"Create a new scenario"**.
2.  Click the big purple **"+"** button.
3.  Search for **"PhoneGrid"** in the list.
4.  Select the app icon.

## Step 2: Select the Action
You will see a list of available actions. To mirror the Zapier functionality (running automation templates), choose:

* **Action:** `Create Cloud Phone Task` (or `Run Automation Template`)
* *(Note: If you want to start a local browser profile, select `Start Browser Profile` instead.)*

---

## Step 3: Create a Connection (Authentication)
Unlike the HTTP method, you only need to do this once.

1.  Click **"Add"** next to the Connection field.
2.  **Connection Name:** Give it a name (e.g., "My PhoneGrid Account").
3.  **App ID:** Paste your App ID.
4.  **Secret Key:** Paste your Secret Key.
5.  Click **Save**. Make will verify your credentials automatically.

[How to get API ID and API KEY?](https://guide.phonegrid.com/api-reference/open-api#get-started-with-phonegrid-open-apis)
---

## Step 4: Configure the Task (Visual Mapping)
Now you will see a form similar to Zapier's, but with Make's drag-and-drop magic.

### 1. Cloud Phone ID
* **Static:** Select your cloud phone from the dropdown list (if available).
* **Dynamic:** If you want to run this on different phones based on a trigger (e.g., a Google Sheet row), toggle the **"Map"** switch and drag the `Phone ID` bubble from the previous module.

### 2. Template ID
* Enter the **Template ID** you want to run (e.g., "TikTok Auto-Scroll").
* You can find this ID in your PhoneGrid Template Market.

### 3. Task Name
* Give your task a unique name, e.g., `Make-Auto-Task-{{now}}`.

### 4. Template Parameters (JSON)
This is where Make shines. You need to pass the parameters for your template (like the target URL).

* **Key:** `url` | **Value:** `{{1.link_column}}` (Mapped from Google Sheets)
* **Key:** `action` | **Value:** `like_and_comment`

> **Pro Tip:** Make usually provides a "Key-Value" collection builder here, so you don't even need to write JSON code! Just click "Add item" and fill in the keys and values.

---

## Step 5: Test the Scenario
1.  Click **"Run once"** in the bottom left corner.
2.  Watch the logic flow. If the PhoneGrid module turns **Green**, the task has been successfully sent to the cloud.
3.  Check your PhoneGrid client or dashboard to see the cloud phone starting up!

---

## Troubleshooting
* **Connection Error:** Ensure your API Key hasn't regenerated.
* **Task Not Starting:** Check if your Cloud Phone has enough "Energy" or subscription time.
* **Parameter Error:** Make sure your Template Parameters match exactly what the script expects (case-sensitive).
