---
title: Call Template via HTTP
tags:
  - Document
  - Tutorial
  - Trigger MoreLogin Template Externally
description: >-
  Before calling any functional APIs, you must exchange your credentials for a
  JWT Access Token.
---
# Call Template via HTTP


## 1. Get Authorization (OAuth2 Token)

Before calling any functional APIs, you must exchange your credentials for a **JWT Access Token**.

* **Endpoint:** `POST https://api.morelogin.com/oauth2/token`
* **Official Docs:** [Authorization Path](https://guide.morelogin.com/api-reference/open-api/open-api/authorization/paths/~1oauth2~1token/post)

### Request (cURL)

```bash
curl -i -X POST \
  https://api.morelogin.com/oauth2/token \
  -H 'Content-Type: application/json' \
  -d '{
    "client_id": 1672940217990530,
    "client_secret": "your_client_secret",
    "grant_type": "client_credentials"
  }'
```

### Response Example

```json
{
    "code": 0,
    "data": {
        "access_token": "eyJhbGciOiJIUzI1NiIsIn...",
        "token_type": "Bearer",
        "expires_in": 3600
    }
}
```

---

## 2. Execute Cloud Phone Template

Use the access_token obtained from Step 1 to trigger a specific RPA template.

* **Endpoint:** `POST https://api.morelogin.com/cloudphone/rpa/onceTask/save`
* **Official Docs:** [Execute Schedule Path](https://guide.morelogin.com/api-reference/open-api/open-api/cloud-phoneschedules-management/paths/~1cloudphone~1rpa~1oncetask~1save/post)

### Request (cURL)

```bash
curl -i -X POST \
  https://api.morelogin.com/cloudphone/rpa/onceTask/save \
  -H 'Authorization: Bearer <YOUR_JWT_HERE>' \
  -H 'Content-Type: application/json' \
  -d '{
    "cloudPhoneId": 16783319661123,
    "scheduleName": "test_automation",
    "templateId": 1678347487160256,
    "templateParameter": "{\"Video Caption\": \"Hello World\", \"AI Label\": true}",
    "description": "schedule description"
  }'
```

---

## 3. Parameter Breakdown

### How to get IDs?

* **Authorization:** Obtained via the `/oauth2/token` endpoint.
* **cloudPhoneId:** Found in the MoreLogin Cloud Phone dashboard (numeric ID).
* **templateId:** Found in the Automation Template market or personal template list.

### Understanding templateParameter

This is a stringified JSON object. You must define the keys based on the template's requirements and then escape them as a string.

**Template Definition Example:**

```json
{
    "Video Caption": "string",
    "AI Label": "boolean",
    "Product Id": "number",
    "Get Leads": "boolean",
    "Comment": "string"
}
```

**How to map it in your request:**

To pass values for the above definition, your templateParameter value should look like this:

```json
{
    "templateParameter": "{\"Video Caption\": \"My Title\", \"AI Label\": true, \"Product Id\": 12345}"
}
```

---

## 4. Error Handling

| Status           | Possible Reason                                              |
| ---------------- | ------------------------------------------------------------ |
| 401 Unauthorized | Token expired or invalid client credentials.                 |
| 400 Bad Request  | Invalid cloudPhoneId or malformed JSON in templateParameter. |
| 404 Not Found    | The templateId does not exist.                               |

---

## Python Quick Start

```python
import requests
import json

def run_morelogin_task():
    # 1. Auth
    auth_res = requests.post(
        "https://api.morelogin.com/oauth2/token",
        json={
            "client_id": 1672940217990530,
            "client_secret": "your_secret",
            "grant_type": "client_credentials"
        }
    )
    token = auth_res.json()['data']['access_token']

    # 2. Execute
    task_payload = {
        "cloudPhoneId": 16783319661123,
        "templateId": 1678347487160256,
        "templateParameter": json.dumps({
            "Video Caption": "My Post",
            "AI Label": True
        })
    }
    
    headers = {"Authorization": f"Bearer {token}"}
    response = requests.post(
        "https://api.morelogin.com/cloudphone/rpa/onceTask/save",
        json=task_payload,
        headers=headers
    )
    return response.json()

print(run_morelogin_task())
```
