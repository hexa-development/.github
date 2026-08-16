<div align="center">

# 🤠 Hexa Framework

**Framework & scripts for RedM roleplay servers**

[![Docs](https://img.shields.io/badge/docs-hexa--docs-b45309?style=for-the-badge)](https://hexa-development.github.io/hexa-docs/)
[![RedM](https://img.shields.io/badge/game-RedM-8b0000?style=for-the-badge)](https://redm.net/)
[![Lua](https://img.shields.io/badge/lua-5.4-2c2d72?style=for-the-badge&logo=lua)](https://www.lua.org/)

</div>

---

## 📦 Projects

| Repository | Description |
| --- | --- |
| [**hexa_core**](https://github.com/hexa-development/hexa_core) | The core framework — players, jobs, items, money, status, callbacks, and permissions in a single resource. ESX-style structure |
| [**hexa-bridge**](https://github.com/hexa-development/hexa-bridge) | Compatibility bridges — run RSG/VORP scripts on hexa_core without code changes |
| [**hexa-docs**](https://github.com/hexa-development/hexa-docs) | Documentation website, built with VitePress (Vue.js) |

## 🚀 Getting started

Read the full installation guide and API reference at

### 👉 [hexa-development.github.io/hexa-docs](https://hexa-development.github.io/hexa-docs/)

```lua
-- grab the core object from your resource
local HexaCore = exports['hexa_core']:GetCoreObject()

local Player = HexaCore.Functions.GetPlayer(source)
Player.Functions.AddMoney('cash', 100, 'welcome bonus')
```

## 🛠️ Tech Stack

- **Lua 5.4** — all scripts run on FXServer (RedM)
- **MariaDB / MySQL** via [oxmysql](https://github.com/CommunityOx/oxmysql)
- **VitePress + Vue.js** — documentation site

---

<div align="center">

*Ride horses. Write code.* 🐎

</div>
