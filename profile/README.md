<div align="center">

# 🤠 Hexa Development

**เฟรมเวิร์กและสคริปต์สำหรับเซิร์ฟเวอร์ RedM Roleplay**

*Framework & scripts for RedM roleplay servers*

[![Docs](https://img.shields.io/badge/docs-hexa--docs-b45309?style=for-the-badge)](https://hexa-development.github.io/hexa-docs/)
[![RedM](https://img.shields.io/badge/game-RedM-8b0000?style=for-the-badge)](https://redm.net/)
[![Lua](https://img.shields.io/badge/lua-5.4-2c2d72?style=for-the-badge&logo=lua)](https://www.lua.org/)

</div>

---

## 📦 โปรเจกต์หลัก

| Repository | คำอธิบาย |
| --- | --- |
| [**hexa_core**](https://github.com/hexa-development/hexa_core) | เฟรมเวิร์กหลัก — ระบบผู้เล่น อาชีพ ไอเทม เงิน สถานะ callbacks และ permission ครบในตัวเดียว โครงสร้างสไตล์ ESX |
| [**hexa-docs**](https://github.com/hexa-development/hexa-docs) | เว็บไซต์เอกสารประกอบการใช้งาน สร้างด้วย VitePress (Vue.js) |

## 🚀 เริ่มต้นใช้งาน

อ่านคู่มือติดตั้งและ API Reference ฉบับเต็มได้ที่

### 👉 [hexa-development.github.io/hexa-docs](https://hexa-development.github.io/hexa-docs/)

```lua
-- ดึง core object จาก resource ของคุณ
local HexaCore = exports['hexa_core']:GetCoreObject()

local Player = HexaCore.Functions.GetPlayer(source)
Player.Functions.AddMoney('cash', 100, 'welcome bonus')
```

## 🛠️ Tech Stack

- **Lua 5.4** — สคริปต์ทั้งหมดบน FXServer (RedM)
- **MariaDB / MySQL** ผ่าน [oxmysql](https://github.com/CommunityOx/oxmysql)
- **VitePress + Vue.js** — เว็บเอกสาร

---

<div align="center">

*สุภาพบุรุษแดนเถื่อน ขี่ม้า เขียนโค้ด* 🐎

</div>
