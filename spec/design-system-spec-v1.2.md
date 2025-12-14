# Design System Spec v1.2 – RGB Effect (Experimental)

> **Type:** Experimental / Additive Extension
>
> **Extends:** Design System Spec v1.1
>
> **Status:** Experimental (Opt-in only)

---

## 1. Purpose & Philosophy

The **RGB Effect** is an **experimental visual accent**, inspired by subtle keyboard backlight aesthetics.

Design goals:
- Add a *personal signature* without breaking system consistency
- Preserve usability and readability
- Remain **decorative**, never functional

The RGB effect is **not a core design element**.

---

## 2. Scope of Application (Strict)

### Allowed Scope

RGB effect MAY be applied ONLY to:
- Decorative containers
- Highlight frames
- Non-interactive background accents

### Forbidden Scope

RGB effect MUST NOT be applied to:
- Text content
- Icons
- Primary interactive surfaces
- Core components (Button, Tag, Knob, Sidebar)

---

## 3. Interaction Rules

- RGB effect is **static or subtly animated**
- It MUST NOT react to hover, press, focus, or state changes
- Animation, if present, must be slow and non-distracting

---

## 4. Visual Characteristics

### Color Behavior

- Uses a **continuous gradient spectrum** (red → green → blue)
- No hard color stops
- Low saturation, soft blending

### Intensity Constraints

- RGB effect must remain below primary UI contrast
- It must never overpower Button Blue or Green

---

## 5. Token Requirements

RGB effect introduces the following **new tokens**:

```txt
--rgb-gradient
--rgb-opacity
--rgb-animation-duration
```

These tokens MUST be defined in `base.css v1.2` or later.

---

## 6. Animation Constraints

- Animation is OPTIONAL
- If enabled:
  - Duration MUST be >= 8s
  - Timing MUST be linear
  - Loop MUST be infinite and seamless

No keyframe definitions are allowed outside token scope.

---

## 7. Relationship to AI-ready Contract

- RGB effect is **disabled by default**
- AI MUST NOT use RGB effect unless explicitly enabled in Contract
- Any use without enablement is invalid

---

## 8. Backward Compatibility

- No impact on Spec v1.0 or v1.1
- Projects not opting in remain visually unchanged

---

## 9. Summary for AI

- RGB effect is decorative only
- Never interactive
- Never dominant
- Always opt-in

---

**End of Design System Spec v1.2 – RGB Effect (Experimental)**

