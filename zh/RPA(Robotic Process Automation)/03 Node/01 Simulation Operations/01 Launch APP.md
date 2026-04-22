---
title: 01 Launch APP
tags:
  - Document
  - Tutorial
  - Simulation Operations
description: >-
  -
  应用程序包名称。您可以通过【开发者工具】(../../02%20Using%20RPA/04%20Developer%20Tools.md)查找指定APP的包名
---
# 启动应用程序

## 节点参数

- **[包名称]** ([String](../../05%20附录/01%20Supported%20Field%20Types.md))
  - 应用程序包名称。您可以通过【开发者工具】(../../02%20Using%20RPA/04%20Developer%20Tools.md)查找指定APP的包名
- **[URI 地址]** （可选）（[String](../../05%20附录/01%20Supported%20Field%20Types.md)）
  - 全称是统一资源标识符。 URI取决于APP是否定义了URI。例如，TikTok的URI是页面链接地址。

## 输出

- **输出参数**
    - 无
- **执行日志**
    - 开始时间
    - 结束时间
    - 持续时间（毫秒）
    - 状态（成功/失败）

## 示例

例如，打开Goolge Play并跳转到Tiktok的页面。如果您只需要打开Goolge Play，则不需要填写URI地址。

|字段名称 |字段值 |
| ---------------- | ------------------------------------------------------------------------ |
| **包名称** | `com.android.vending` |
| **URI 地址** | `https://play.google.com/store/search?q=tiktok&c=apps&hl=en` |

节点输出参数：无

## 常用APP包名

|应用程序名称 |套餐名称 |
| :---------------- | ：------------------------------------------ |
| TikTok（主要）| com.zhiliaoapp.musically 或 com.tiktok.android |
| TikTok 精简版 | com.ss.android.ugc.trill.lite |
| YouTube | com.google.android.youtube |
| Instagram | com.instagram.android |
|脸书 | com.facebook.katana |
| Facebook 精简版 | com.facebook.lite |
| X（推特）| com.twitter.android |
| X（非官方）| com.x.android |
|主题 | com.instagram.巴塞罗那 |
| WhatsApp | com.whatsapp 元 |
| WhatsApp 业务 | com.whatsapp.w4b |
|快照 | com.snapchat.android |
|电报 | org.telegram.messenger |
|电报 X | org.telegram.messenger.x |
|红迪网 | com.reddit.frontpage |

## 相关节点

[关闭APP](./02%20Close%20APP.md)
