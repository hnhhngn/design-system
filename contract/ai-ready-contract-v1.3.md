# AI-ready Contract v1.3 – Allow RGB Effect (Experimental)

> **Type:** Additive Update (Non-breaking)
>
> **Extends:** AI-ready Contract v1.2
>
> **Purpose:** Explicitly allow the **RGB Effect (Experimental)** under strict, opt-in, and scope-limited rules.

---

## 1. Contract Metadata

```json
{
  "contract_version": "1.3",
  "extends": "AI-ready Contract v1.2",
  "change_type": "additive",
  "stability": "experimental"
}
```

---

## 2. Feature Enablement

```json
{
  "experimental_features": {
    "rgb_effect": {
      "enabled": true,
      "default": false
    }
  }
}
```

Meaning:
- RGB Effect is **available but disabled by default**
- Explicit opt-in is required via `CURRENT.md`

---

## 3. Allowed Scope (Mandatory)

```json
{
  "rgb_effect_scope": {
    "allowed_targets": [
      "decorative-container",
      "background-frame",
      "non-interactive-accent"
    ]
  }
}
```

AI MAY:
- Apply RGB effect only as a **visual layer**

AI MUST NOT:
- Apply RGB effect to interactive components
- Bind RGB effect to state changes (hover, active, focus)

---

## 4. Forbidden Usage (Strict)

```json
{
  "rgb_effect_forbidden": {
    "targets": [
      "text",
      "icon",
      "button",
      "tag",
      "knob",
      "sidebar",
      "form-control"
    ]
  }
}
```

Any violation invalidates the output.

---

## 5. Token Dependency Enforcement

```json
{
  "token_requirements": {
    "rgb_effect": [
      "--rgb-gradient",
      "--rgb-opacity",
      "--rgb-animation-duration"
    ]
  }
}
```

Rules:
- If any token is missing, AI MUST stop and ask
- AI MUST NOT hard-code gradients or animation values

---

## 6. Animation Constraints

```json
{
  "rgb_animation_rules": {
    "min_duration_seconds": 8,
    "timing_function": "linear",
    "loop": "infinite",
    "interaction_bound": false
  }
}
```

---

## 7. Opt-in Requirement

RGB Effect may be used **ONLY IF**:
- `CURRENT.md` explicitly enables it

Otherwise:
- RGB Effect is considered **disabled**

---

## 8. Backward Compatibility

- Projects using Contract v1.2 or lower are unaffected
- No core component behavior is modified

---

## 9. Failure Conditions

Output is **invalid** if AI:
- Uses RGB Effect without Contract v1.3
- Uses RGB Effect without explicit opt-in
- Violates scope or animation constraints

---

## 10. Summary for AI (Critical)

- RGB Effect is experimental
- Decorative only
- Never interactive
- Always opt-in

---

**End of AI-ready Contract v1.3 – Allow RGB Effect (Experimental)**