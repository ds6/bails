# 🔄 Migration Guide: From `bails` to `buils` (Compatible with Baileys 7.x – ESM Only)

WhatsApp has recently introduced important internal changes, including new WhatsApp Web versions and protocol updates.  
Because of these changes, if you are still using the **bails** repository, it is strongly recommended to migrate to **buils**, which already includes support for the latest **Baileys 7.x** version.

---

## 🔗 Repository Links

| Project | URL |
|--------|-----|
| 📁 Old repository (`bails`) | https://github.com/ds6/bails |
| 📁 New recommended repository (`buils`) | https://github.com/ds6/buils |

The **buils** repository is fully prepared for modern Baileys usage and WhatsApp's recent updates.

---

## 📌 Important Changes in Baileys 7.x

Baileys is now **100% ESM Only**, which means:

- You can no longer use `require()` directly.
- If your environment is CommonJS (CJS), you must import the default export manually.
- If your environment is ESM, you do **not** use `.default`.
- The import structure has been updated and expanded.

---

## 🟨 Using Baileys in CommonJS (CJS)

Because Baileys 7.x is ESM Only, the correct way to import it in CJS is:

```js
const baileys = require('@whiskeysockets/baileys').default;

const {
    makeWASocket,
    fetchLatestBaileysVersion,
    DisconnectReason
} = baileys;
```

## 🟦 Using Baileys in ESM (Recommended)
If your project uses ESM (for example "type": "module" in package.json), the correct and updated import format is:

```js
import {
    makeWASocket,
    fetchLatestBaileysVersion,
    DisconnectReason
} from '@whiskeysockets/baileys';
```
