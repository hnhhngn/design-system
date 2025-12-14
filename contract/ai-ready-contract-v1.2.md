# AI-ready Contract v1.2 – Allow Button Yellow

> **Type:** Additive Update (Non-breaking)
>
> **Extends:** AI-ready Contract v1.1
>
> **Purpose:** Explicitly allow the use of **Button Yellow variant** under controlled rules, without modifying any existing core behaviors.

---

## 1. Contract Metadata

```json
{
  "contract_version": "1.2",
  "extends": "AI-ready Contract v1.1",
  "change_type": "additive"
}
```

---

## 2. Variant Enablement

```json
{
  "component_variants": {
    "button": {
      "allowed_variants": ["blue", "green", "yellow"]
    }
  }
}
```

Meaning:
- Button Yellow is now a **valid variant** under v1.x
- Button Blue and Green remain unchanged

---

## 3. Usage Constraints (Mandatory)

```json
{
  "button_yellow_rules": {
    "max_instances_per_view": 1,
    "requires_primary_present": true,
    "allowed_roles": [
      "secondary-highlight",
      "attention-confirmation"
    ],
    "forbidden_roles": [
      "primary-action",
      "destructive-action"
    ]
  }
}
```

AI MUST:
- Ensure Button Blue exists when Button Yellow is used
- Limit Button Yellow to **one instance per view**

AI MUST NOT:
- Replace primary actions with Button Yellow
- Use Button Yellow for destructive or irreversible actions

---

## 4. Token Dependency Enforcement

```json
{
  "token_requirements": {
    "button.yellow": [
      "--button-yellow-bg",
      "--button-yellow-shadow",
      "--button-yellow-shadow-pressed"
    ]
  }
}
```

Rules:
- If any required token is missing, AI MUST stop and ask
- AI MUST NOT substitute with other button tokens

---

## 5. Backward Compatibility

- Projects using Contract v1.0 or v1.1 are unaffected
- Button Yellow is **disabled** unless Contract v1.2 is explicitly applied

---

## 6. Failure Conditions

Output is **invalid** if AI:
- Uses Button Yellow without Contract v1.2
- Uses Button Yellow without required tokens
- Violates usage constraints

---

## 7. Summary for AI (Critical)

- Button Yellow is **allowed but constrained**
- Behavior is inherited, not customized
- Consistency takes precedence over emphasis

---

**End of AI-ready Contract v1.2 – Allow Button Yellow**