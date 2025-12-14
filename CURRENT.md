# Design System – CURRENT

> This file defines the **single active runtime state** of the personal AI-driven Design System.
>
> It is the **only authoritative entry point** for both AI and human users to determine which rules, tokens, and features are currently enabled.

---

## Active Versions

- **Design System Spec:** `design-system-spec-v1.2.md`
- **AI-ready Contract:** `ai-ready-contract-v1.3.md`
- **Token Runtime:** `base.css`

  - Source: `base.v1.2.css`

---

## Enabled Features

- Button Yellow (secondary highlight variant)
- RGB Effect (Experimental, decorative only)

---

## Disabled / Not Available

- Any button variants other than Blue, Green, Yellow
- RGB usage outside decorative / ambient scope
- RGB on interactive or core components

---

## Core Guarantees

- Core components are **locked and stable**:

  - Button
  - Knob
  - Sidebar
  - Tag

- No core behavior may be modified under Design System v1.x

- All UI must be **token-driven**

- `base.css` is **read-only** for AI and applications

---

## AI Usage Instructions (Mandatory)

When generating or modifying UI, AI MUST follow this sequence:

1. Read this file (`CURRENT.md`)
2. Load the referenced **Design System Spec** and **AI-ready Contract**
3. Consume tokens exclusively from `base.css`
4. Apply only features explicitly listed as **Enabled**
5. Treat anything not listed here as **not allowed**

If a required capability is missing, AI MUST stop and ask before proceeding.

---

## Update Rules

- This file is updated **only when the active Design System state changes**
- Historical Spec / Contract / token files are never modified
- Any change in this file represents an **explicit opt-in** to new behavior or visuals

---

## Machine-Readable Guarantee

The content of this file is structured so it can be converted **1:1** into a machine-readable `active.json` format **without loss of information**.

---

**End of CURRENT.md**
