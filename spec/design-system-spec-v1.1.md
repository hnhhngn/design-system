# Design System Spec v1.1 – Button Yellow Variant

> **Type:** Additive Update (Non-breaking)
>
> **Extends:** Design System Spec v1.0
>
> **Status:** Stable Extension

---

## 1. Scope of This Update

This update introduces **Button Yellow** as a **new variant** of the existing Button component.

- No existing components are modified
- No existing tokens are changed
- No behaviors are redefined

This update is fully compatible with **v1.0 consumers**.

---

## 2. Purpose of Button Yellow

### Semantic Role

**Button Yellow** represents:
- Secondary-highlight actions
- Attention-required confirmation
- Non-destructive warning acknowledgement

It is designed to **draw attention without replacing primary intent**.

---

## 3. Usage Rules (Strict)

### Allowed Usage

- Secondary call-to-action when **Button Blue already exists** on screen
- Highlighted confirmation steps ("Continue", "Review", "Proceed")
- Limited to **maximum one instance per view**

### Forbidden Usage

- Must NOT replace Button Blue as primary action
- Must NOT be used for destructive actions
- Must NOT appear multiple times in the same interaction group

---

## 4. Visual & Interaction Behavior

### Inherited Behavior

Button Yellow **inherits all interaction behaviors** from core Button:
- 3D press effect
- Default / Active states
- Motion timing

No custom animation or interaction is introduced.

---

## 5. Token Requirements

Button Yellow requires the following **new tokens**:

```txt
--button-yellow-bg
--button-yellow-shadow
--button-yellow-shadow-pressed
```

> These tokens MUST be defined in `base.css v1.1` or later.

No existing tokens are modified.

---

## 6. Relationship to AI-ready Contract

- Button Yellow is **not available** unless Contract v1.1+ explicitly allows it
- AI MUST ask for confirmation if Button Yellow is requested under v1.0

---

## 7. Backward Compatibility

- Projects using **Spec v1.0** are unaffected
- Projects opting into **Spec v1.1** gain access to Button Yellow

---

## 8. Summary for AI

- Button Yellow is a **variant**, not a new component
- Semantics are limited and controlled
- Behavior is inherited, not redefined

---

**End of Design System Spec v1.1 – Button Yellow**

