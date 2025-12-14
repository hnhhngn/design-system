# Design System – CURRENT

> This file defines the **single active state** of the personal AI-driven Design System.
>
> It is the **only entry point** that AI and humans should read to understand which rules, tokens, and capabilities are currently in effect.

---

## Active Versions

- **Design System Spec:** `design-system-spec-v1.1.md`
- **AI-ready Contract:** `ai-ready-contract-v1.2.md`
- **Token Runtime:** `base.css`
  - Source: `base.v1.1.css`

---

## Enabled Features

- Button Yellow (secondary highlight variant)

---

## Disabled / Not Available

- RGB / decorative glow effects
- Any button variants other than Blue, Green, Yellow

---

## Core Guarantees

- Core components are locked:
  - Button
  - Knob
  - Sidebar
  - Tag
- No core behavior may be modified under v1.x
- All UI must be token-driven
- `base.css` is **read-only** for AI and applications

---

## Usage Instruction for AI

When generating UI, follow this process strictly:

1. Read this file (`CURRENT.md`)
2. Load the referenced Spec and Contract versions
3. Consume tokens from `base.css`
4. Do NOT assume availability of anything not listed here

---

## Update Rule

- This file is updated **only when the active Design System state changes**
- Historical versions remain untouched
- Any change here represents an **explicit opt-in** to new capabilities

---

## Machine-Readable Mapping (Non-authoritative)

The content of this file can be directly mapped to an equivalent `active.json` structure without loss of information.

---

**End of CURRENT.md**

