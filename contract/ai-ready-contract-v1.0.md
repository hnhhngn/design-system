# AI-ready Contract v1.0 – UI System

> **Status:** Enforced / Machine-readable
>
> **Purpose:** Tài liệu này là **hợp đồng cưỡng chế** dành cho AI khi sinh UI. Nó không giải thích *vì sao*, mà chỉ định *được làm gì / không được làm gì*.
>
> Contract này **tham chiếu trực tiếp** đến *Design System Spec v1.0* và **không thay thế Spec**.

---

## 1. Contract Scope

```json
{
  "design_system": "Design System Spec v1.0 – AI-driven UI",
  "contract_version": "1.0",
  "mode": "locked-core",
  "update_policy": "additive-only"
}
```

---

## 2. Authority & Priority

### Priority Order (cao → thấp)
1. **AI-ready Contract v1.0** (this document)
2. **Design System Spec v1.0**
3. Generated code (HTML / CSS / JS)

If any conflict exists, **higher priority overrides lower priority**.

---

## 3. Token Enforcement Rules

```json
{
  "token_policy": {
    "require_token_reference": true,
    "allow_hardcoded_values": false,
    "allowed_units": ["px", "%", "ms", "deg", "rgba"],
    "color_invention": false,
    "shadow_invention": false,
    "motion_invention": false
  }
}
```

Rules:
- Every visual value MUST reference a token
- No raw hex / rgb / hsl values unless explicitly defined as token

---

## 4. CSS Generation Policy

```json
{
  "css_generation": {
    "allowed": true,
    "must_be_token_driven": true,
    "naming_convention": "free",
    "forbidden_patterns": [
      "inline-style",
      "magic-numbers",
      "unscoped-animation"
    ]
  }
}
```

---

## 5. Core Component Lock

```json
{
  "locked_components": {
    "button": {
      "variants": ["blue", "green"],
      "behavior": "immutable"
    },
    "knob": {
      "interaction_model": "immutable"
    },
    "sidebar": {
      "layout_logic": "immutable"
    },
    "tag": {
      "states": ["inactive", "active"],
      "semantics": "immutable"
    }
  }
}
```

AI MUST NOT:
- Change default behaviors
- Swap component semantics
- Override interaction rules

---

## 6. Extension Control

```json
{
  "extensions": {
    "allowed": true,
    "allowed_types": ["variant", "effect", "new-component"],
    "require_declaration": true
  }
}
```

Rules:
- Extensions MUST be explicitly declared
- No silent extension or implicit behavior change

---

## 7. Experimental & Effects (RGB example)

```json
{
  "effects": {
    "rgb_glow": {
      "allowed": false,
      "scope": [],
      "max_instances": 0
    }
  }
}
```

> Note: Effects are **disabled by default**. Enabling requires a contract update (v1.x).

---

## 8. Missing Information Handling

```json
{
  "missing_information_policy": {
    "on_missing_token": "ask",
    "on_missing_variant": "ask",
    "on_missing_behavior": "ask"
  }
}
```

AI MUST:
1. Stop generation
2. Ask a clarification question
3. Wait for confirmation

---

## 9. Version Compliance

```json
{
  "versioning": {
    "current": "1.0",
    "allow_auto_upgrade": false,
    "breaking_change_allowed": false
  }
}
```

AI MUST NOT assume newer versions.

---

## 10. Failure Conditions

If AI violates any rule above:
- Output is considered **invalid**
- UI must be regenerated after correction

---

## 11. Contract Summary (For AI)

- This contract is **not optional**
- Spec explains meaning, Contract enforces behavior
- Consistency > Creativity

---

**End of AI-ready Contract v1.0**

