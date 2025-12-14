# AI-ready Contract v1.1 – base.css Lock Extension

> **Type:** Additive Update (Non-breaking)
>
> **Depends on:** AI-ready Contract v1.0
>
> **Purpose:** Khóa `base.css` ở chế độ **read-only token runtime**, ngăn AI hoặc con người vô tình phá Design System ở tầng implementation.

---

## 1. Contract Metadata

```json
{
  "contract_version": "1.1",
  "extends": "AI-ready Contract v1.0",
  "change_type": "additive"
}
```

---

## 2. base.css Authority Declaration

```json
{
  "base_css": {
    "role": "token-runtime",
    "source_of_truth": "Design System Spec v1.x",
    "editable": false
  }
}
```

Meaning:
- `base.css` chỉ là **materialized tokens**
- Không chứa logic, layout, hay component implementation

---

## 3. Allowed Content in base.css

```json
{
  "base_css_policy": {
    "allowed_content": [
      "css-variable-definition",
      "token-comment"
    ]
  }
}
```

Allowed examples:
```css
:root {
  --color-surface-root: #e3e4e6;
}
```

---

## 4. Forbidden Content in base.css

```json
{
  "base_css_policy": {
    "forbidden_content": [
      "class-selector",
      "id-selector",
      "element-selector",
      "media-query",
      "keyframes",
      "animation",
      "layout-rule",
      "component-style"
    ]
  }
}
```

Forbidden examples:
```css
.button { ... }
@media (max-width: 768px) { ... }
```

---

## 5. AI Behavior Enforcement

```json
{
  "ai_enforcement": {
    "can_read_base_css": true,
    "can_modify_base_css": false,
    "can_generate_base_css": false
  }
}
```

Rules:
- AI chỉ được **consume** token từ `base.css`
- AI không được đề xuất chỉnh sửa `base.css` trừ khi được yêu cầu explicit

---

## 6. Versioning Rules

```json
{
  "versioning": {
    "base_css_version": "1.0",
    "upgrade_requires": "explicit-user-request"
  }
}
```

AI MUST NOT:
- Tự động nâng version `base.css`
- Sửa token để "phù hợp hơn" với UI

---

## 7. Failure Conditions

If any output:
- Writes into `base.css`
- Suggests token edits without request

→ Output is **invalid under Contract v1.1**.

---

## 8. Summary for AI (Critical)

- `base.css` is **read-only**
- Tokens are **consumed, not designed**
- UI code must adapt to tokens, not the reverse

---

**End of AI-ready Contract v1.1 – base.css Lock**

