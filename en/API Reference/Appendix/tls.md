## Disable TLS Protocol and Correspondence Between Value

> **Note**: This feature requires **PhoneGrid version V2.36.0 or higher**.

### Overview

This article provides the mapping between TLS cipher suite names and their hexadecimal identifiers for both **Chrome** and **Firefox** browser profiles in PhoneGrid. These values can be used when configuring or disabling specific TLS protocols within browser fingerprints.

---

### Chrome Cipher Suite Mapping

| Cipher Suite Name                                      | Hex Value   |
|--------------------------------------------------------|-------------|
| `TLS_AES_128_CCM_8_SHA256`                             | `0x1305`    |
| `TLS_AES_128_CCM_SHA256`                               | `0x1304`    |
| `TLS_DHE_RSA_WITH_AES_128_CBC_SHA`                     | `0x0033`    |
| `TLS_DHE_RSA_WITH_AES_128_CBC_SHA256`                  | `0x0067`    |
| `TLS_DHE_RSA_WITH_AES_128_GCM_SHA256`                  | `0x009E`    |
| `TLS_DHE_RSA_WITH_AES_256_CBC_SHA`                     | `0x0039`    |
| `TLS_DHE_RSA_WITH_AES_256_CBC_SHA256`                  | `0x006B`    |
| `TLS_DHE_RSA_WITH_AES_256_GCM_SHA384`                  | `0x009F`    |
| `TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA`                 | `0xC009`    |
| `TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA256`              | `0xC023`    |
| `TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256`              | `0xC02B`    |
| `TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA`                 | `0xC00A`    |
| `TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA384`              | `0xC024`    |
| `TLS_ECDHE_ECDSA_WITH_AES_256_GCM_SHA384`              | `0xC02C`    |
| `TLS_ECDHE_ECDSA_WITH_CHACHA20_POLY1305_SHA256`        | `0xCCA9`    |
| `TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA`                   | `0xC013`    |
| `TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256`                | `0xC027`    |
| `TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256`                | `0xC02F`    |
| `TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA`                   | `0xC014`    |
| `TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384`                | `0xC028`    |
| `TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384`                | `0xC030`    |
| `TLS_ECDHE_RSA_WITH_CHACHA20_POLY1305_SHA256`          | `0xCCA8`    |
| `TLS_RSA_WITH_AES_128_CBC_SHA`                         | `0x002F`    |
| `TLS_RSA_WITH_AES_128_CBC_SHA256`                      | `0x003C`    |
| `TLS_RSA_WITH_AES_128_GCM_SHA256`                      | `0x009C`    |
| `TLS_RSA_WITH_AES_256_CBC_SHA`                         | `0x0035`    |
| `TLS_RSA_WITH_AES_256_CBC_SHA256`                      | `0x003D`    |
| `TLS_RSA_WITH_AES_256_GCM_SHA384`                      | `0x009D`    |

---

### Firefox Cipher Suite Mapping

| Cipher Suite Name                                      | Hex Value   |
|--------------------------------------------------------|-------------|
| `TLS_DHE_RSA_WITH_AES_128_CBC_SHA`                     | `0x0033`    |
| `TLS_DHE_RSA_WITH_AES_256_CBC_SHA`                     | `0x0039`    |
| `TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA`                 | `0xC009`    |
| `TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256`              | `0xC02B`    |
| `TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA`                 | `0xC00A`    |
| `TLS_ECDHE_ECDSA_WITH_AES_256_GCM_SHA384`              | `0xC02C`    |
| `TLS_ECDHE_ECDSA_WITH_CHACHA20_POLY1305_SHA256`        | `0xCCA9`    |
| `TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA`                   | `0xC013`    |
| `TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256`                | `0xC02F`    |
| `TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA`                   | `0xC014`    |
| `TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384`                | `0xC030`    |
| `TLS_ECDHE_RSA_WITH_CHACHA20_POLY1305_SHA256`          | `0xCCA8`    |
| `TLS_RSA_WITH_3DES_EDE_CBC_SHA`                        | `0x000A`    |
| `TLS_RSA_WITH_AES_128_CBC_SHA`                         | `0x002F`    |
| `TLS_RSA_WITH_AES_128_GCM_SHA256`                      | `0x009C`    |
| `TLS_RSA_WITH_AES_256_CBC_SHA`                         | `0x0035`    |
| `TLS_RSA_WITH_AES_256_GCM_SHA384`                      | `0x009D`    |

---

> 💡 **Tip**: Use these hex values in your browser profile configuration to selectively disable insecure or unwanted TLS cipher suites for enhanced security or compatibility testing.

---
