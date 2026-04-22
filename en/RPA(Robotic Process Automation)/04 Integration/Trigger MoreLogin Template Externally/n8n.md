---
title: n8n
tags:
  - Document
  - Tutorial
  - Trigger MoreLogin Template Externally
description: >-
  1.  Step 1 (Get Token): Send App ID and Secret to /oauth2/token to obtain a
  temporary accesstoken.
---

# n8n

1.  **Step 1 (Get Token):** Send App ID and Secret to `/oauth2/token` to obtain a temporary `access_token`.
2.  **Step 2 (Run Task):** Put the Token in the Header and construct parameters containing **Stringified JSON** to trigger the cloud phone task.

---

## Prerequisites

Before you begin, please make sure you have the following information ready:

1.  **API Credentials** (Get from [MoreLogin Dashboard](https://id.morelogin.com/) -> API Management):
    * `App ID` (i.e., client_id)
    * `Secret Key` (i.e., client_secret)
    [How to get Authorization?](https://guide.morelogin.com/api-reference/open-api/open-api/authorization/paths/~1oauth2~1token/post)
2.  **Resource IDs** (Get from the cloud phone list and template marketplace):
    * `Cloud Phone ID` (numeric only)
    * `Template ID` (numeric only)
    [How to get?](https://guide.morelogin.com/api-reference/open-api/open-api/cloud-phoneschedules-management/paths/~1cloudphone~1rpa~1oncetask~1save/post)
---

## One-Click Workflow Import

To simplify configuration, we have packaged a complete n8n dual-node workflow for you. You don't need to manually handle Token passing and complex JSON escaping.

**Simply copy the JSON code below and paste it (Ctrl+V) into the n8n canvas:**

```json
{
  "nodes": [
    {
      "parameters": {
        "method": "POST",
        "url": "[https://api.morelogin.com/oauth2/token](https://api.morelogin.com/oauth2/token)",
        "sendBody": true,
        "contentType": "json",
        "bodyParameters": {
          "parameters": [
            {
              "name": "client_id",
              "value": "YOUR_APP_ID_HERE"
            },
            {
              "name": "client_secret",
              "value": "YOUR_SECRET_KEY_HERE"
            },
            {
              "name": "grant_type",
              "value": "client_credentials"
            }
          ]
        },
        "options": {}
      },
      "id": "step_1_auth",
      "name": "Step 1: Get Token",
      "type": "n8n-nodes-base.httpRequest",
      "typeVersion": 4.1,
      "position": [
        460,
        300
      ]
    },
    {
      "parameters": {
        "method": "POST",
        "url": "[https://api.morelogin.com/cloudphone/rpa/onceTask/save](https://api.morelogin.com/cloudphone/rpa/onceTask/save)",
        "sendHeaders": true,
        "headerParameters": {
          "parameters": [
            {
              "name": "Authorization",
              "value": "={{ 'Bearer ' + $json.data.access_token }}"
            }
          ]
        },
        "sendBody": true,
        "contentType": "json",
        "bodyParameters": {
          "parameters": [
            {
              "name": "cloudPhoneId",
              "value": 1234567890
            },
            {
              "name": "templateId",
              "value": 1678347487160256
            },
            {
              "name": "scheduleName",
              "value": "n8n-Auto-Task"
            },
            {
              "name": "description",
              "value": "Triggered via n8n"
            },
            {
              "name": "templateParameter",
              "value": "={{ JSON.stringify({\n    \"Video Caption\": \"My Automation Video\",\n    \"AI Label\": true,\n    \"Product Id\": 1001,\n    \"Get Leads\": false,\n    \"Comment\": \"Great content!\"\n}) }}"
            }
          ]
        },
        "options": {}
      },
      "id": "step_2_run_task",
      "name": "Step 2: Run Task",
      "type": "n8n-nodes-base.httpRequest",
      "typeVersion": 4.1,
      "position": [
        680,
        300
      ],
      "dependencies": {
        "nodes": [
          {
            "node": "Step 1: Get Token",
            "type": "main",
            "index": 0
          }
        ]
      }
    }
  ],
  "connections": {
    "Step 1: Get Token": {
      "main": [
        [
          {
            "node": "Step 2: Run Task",
            "type": "main",
            "index": 0
          }
        ]
      ]
    }
  }
}
