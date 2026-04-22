---
title: 01 Launch APP
tags:
  - Document
  - Tutorial
  - Simulation Operations
description: '- [Package Name] (String)'
---

# Launch APP

## Node Parameters

- **[Package Name]** ([String](../../05%20附录/01%20Supported%20Field%20Types.md))
  - APP package name. You can find the Package Name of a specified APP via [Developer Tools](../../02%20Using%20RPA/04%20Developer%20Tools.md)
- **[URI Address]** (Optional) ([String](../../05%20附录/01%20Supported%20Field%20Types.md))
  - Full name is Uniform Resource Identifier. URI depends on whether the APP has defined a URI. For example, TikTok's URI is the page link address.

## Output

- **Output Parameters**
    - None
- **Execution Log**
    - Start Time
    - End Time
    - Duration (ms)
    - Status (Success/Failure)

## Example

For example, open Goolge Play and jump to Tiktok's page. If you only need to open Goolge Play, you don't need to fill in the URI address.

| Field Name       | Field Value                                                  |
| ---------------- | ------------------------------------------------------------ |
| **Package Name** | `com.android.vending`                                        |
| **URI Address**  | `https://play.google.com/store/search?q=tiktok&c=apps&hl=en` |

Node Output Parameters: None

## Common APP Package Names

| APP Name          | Package Name                                   |
| :---------------- | :--------------------------------------------- |
| TikTok (Main)     | com.zhiliaoapp.musically or com.tiktok.android |
| TikTok Lite       | com.ss.android.ugc.trill.lite                  |
| YouTube           | com.google.android.youtube                     |
| Instagram         | com.instagram.android                          |
| Facebook          | com.facebook.katana                            |
| Facebook Lite     | com.facebook.lite                              |
| X (Twitter)       | com.twitter.android                            |
| X (Unofficial)    | com.x.android                                  |
| Threads           | com.instagram.barcelona                        |
| WhatsApp          | com.whatsapp Meta                              |
| WhatsApp Business | com.whatsapp.w4b                               |
| Snapchat          | com.snapchat.android                           |
| Telegram          | org.telegram.messenger                         |
| Telegram X        | org.telegram.messenger.x                       |
| Reddit            | com.reddit.frontpage                           |

## Related Nodes

[Close APP](./02%20Close%20APP.md)
