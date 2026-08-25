<div align="center">

# HEXA FRAMEWORK

### A modern RedM framework for building roleplay servers.

**Fast. Modular. Developer-friendly.**

<br>

[![Documentation](https://img.shields.io/badge/Documentation-Hexa_Docs-B45309?style=for-the-badge)](https://hexa-development.github.io/hexa-docs/)
[![RedM](https://img.shields.io/badge/Platform-RedM-8B0000?style=for-the-badge)](https://redm.net/)
[![Lua](https://img.shields.io/badge/Lua-5.4-2C2D72?style=for-the-badge\&logo=lua\&logoColor=white)](https://www.lua.org/)
[![GitHub](https://img.shields.io/badge/GitHub-Hexa_Development-181717?style=for-the-badge\&logo=github)](https://github.com/hexa-development)

<br>

**Framework · Bridge · APIs · Developer Tools**

</div>

---

## About Hexa

**Hexa Framework** is a modular framework designed for building modern **RedM roleplay servers**.

The project focuses on providing a clean foundation for server development without forcing every system into a single massive resource.

`hexa_core` provides the essential server infrastructure, while additional Hexa resources can be added, removed, or replaced independently.

### Core principles

* **Modular** — use only the systems your server needs
* **Developer-friendly** — predictable APIs and project structure
* **Performance-focused** — avoid unnecessary client and server overhead
* **Extensible** — build custom resources directly on top of Hexa
* **Interoperable** — compatibility layers for existing RedM resources
* **Documented** — APIs and installation guides maintained alongside the framework

---

## Projects

| Project                                                          | Description                                                                                                   |
| :--------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------ |
| [`hexa_core`](https://github.com/hexa-development/hexa_core)     | Core framework providing players, jobs, items, money, status, permissions, callbacks, events, and server APIs |
| [`hexa-bridge`](https://github.com/hexa-development/hexa-bridge) | Compatibility layer for integrating supported RSG and VORP resources with Hexa                                |
| [`hexa-docs`](https://github.com/hexa-development/hexa-docs)     | Official Hexa documentation and API reference powered by VitePress                                            |

---

## hexa_core

`hexa_core` is the foundation of the Hexa ecosystem.

It handles shared functionality that other resources can access through a consistent API.

### Included systems

```text
Player Management
├── Player lifecycle
├── Character data
├── Metadata
└── Player state

Economy
├── Cash
├── Bank
└── Money transactions

Jobs
├── Job data
├── Grades
└── Job state

Inventory Integration
├── Items
├── Item metadata
└── Item operations

Server APIs
├── Callbacks
├── Events
├── Exports
└── Shared functions

Administration
├── Permissions
├── Groups
└── Command access
```

---

## Quick Start

Get the Hexa core object from your resource:

```lua
local HexaCore = exports['hexa_core']:GetCoreObject()
```

Access a player:

```lua
local Player = HexaCore.Functions.GetPlayer(source)

if not Player then
    return
end
```

Add money:

```lua
Player.Functions.AddMoney(
    'cash',
    100,
    'welcome_bonus'
)
```

From here, your resource can interact with Hexa through the core API without duplicating player, economy, permission, or callback logic.

---

## Example Resource

```lua
local HexaCore = exports['hexa_core']:GetCoreObject()

RegisterNetEvent('example:server:reward', function()
    local src = source

    local Player = HexaCore.Functions.GetPlayer(src)

    if not Player then
        return
    end

    Player.Functions.AddMoney(
        'cash',
        100,
        'example_reward'
    )
end)
```

---

## Bridge

Already have resources built for another RedM ecosystem?

**hexa-bridge** is designed to reduce migration work by providing compatibility APIs for supported resources.

```text
Existing Resource
       │
       ▼
┌─────────────────┐
│   hexa-bridge   │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│    hexa_core    │
└─────────────────┘
```

The goal is simple:

> Migrate your server progressively instead of rewriting everything at once.

Compatibility depends on the APIs used by each resource. Check the documentation for currently supported bridge functionality.

---

## Architecture

Hexa follows a modular architecture where `hexa_core` acts as the shared foundation.

```text
                    ┌──────────────────┐
                    │    hexa_core     │
                    └────────┬─────────┘
                             │
          ┌──────────────────┼──────────────────┐
          │                  │                  │
          ▼                  ▼                  ▼
   ┌────────────┐     ┌────────────┐     ┌────────────┐
   │ Hexa Script │     │ Hexa Script │     │ Hexa Script │
   └────────────┘     └────────────┘     └────────────┘
          │
          ▼
   ┌─────────────┐
   │ hexa-bridge │
   └──────┬──────┘
          │
          ▼
   Existing RedM Resources
```

This keeps individual systems independent while sharing a common foundation.

---

## Tech Stack

| Technology          | Usage                     |
| :------------------ | :------------------------ |
| **Lua 5.4**         | RedM / FXServer resources |
| **FXServer**        | Server runtime            |
| **MariaDB / MySQL** | Persistent server data    |
| **oxmysql**         | Database communication    |
| **VitePress**       | Documentation             |
| **Vue.js**          | Documentation frontend    |

---

## Documentation

Complete installation instructions, API references, examples, and development guides are available in the official documentation.

### [Open Hexa Documentation →](https://hexa-development.github.io/hexa-docs/)

Documentation includes:

* Installation
* Configuration
* Core API
* Player API
* Money API
* Jobs
* Items
* Callbacks
* Permissions
* Events
* Exports
* Bridge compatibility
* Resource development examples

---

## Repository Structure

A typical Hexa-based server can be organized like this:

```text
resources/
│
├── [hexa]/
│   ├── hexa_core/
│   ├── hexa-bridge/
│   ├── hexa_banking/
│   ├── hexa_notify/
│   └── ...
│
├── [standalone]/
│   └── ...
│
└── [maps]/
    └── ...
```

Each system remains its own resource instead of turning the core into a monolith.

---

## Building with Hexa

A Hexa resource should communicate with the framework through documented APIs rather than directly accessing internal framework data.

```lua
local HexaCore = exports['hexa_core']:GetCoreObject()
```

This provides a stable entry point for:

```text
HexaCore
├── Functions
├── Shared
├── Commands
├── Callbacks
└── Player APIs
```

Keeping resources behind public APIs makes them easier to maintain, update, and reuse.

---

## Development Status

Hexa Framework is under active development.

APIs, bridge compatibility, tooling, and documentation will continue to expand as the ecosystem grows.

For production servers, review release notes before updating core resources.

---

<div align="center">

### Build the world. Define the rules.

**Powered by Hexa Framework**

<br>

[Documentation](https://hexa-development.github.io/hexa-docs/) ·
[GitHub](https://github.com/hexa-development) ·
[RedM](https://redm.net/)

<br>

*Ride horses. Write code.*

</div>
