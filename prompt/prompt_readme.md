# Prompt Set – Personal AI Design System

This folder contains the **only prompts you need** to operate the Personal AI Design System across different AI platforms (ChatGPT, Gemini, etc.).

Design goals:
- One mental model
- Minimal memorization
- Explicit runtime checks
- No rule duplication

---

## Files Overview

```
prompt/
├── 00-init.md            # Session bootstrap (mindset only)
├── 10-runtime-github.md  # Runtime: GitHub repository mode
├── 11-runtime-inline.md  # Runtime: inline CURRENT.md mode (fallback)
├── 20-update-github.md   # Notify update when AI reads GitHub
├── 21-update-inline.md   # Notify update when files are uploaded
└── README.md             # This file
```

---

## Usage Summary (TL;DR)

1. **Start of session / Instructions** → `00-init.md`
2. **Before any UI-related task** → ONE runtime prompt:
   - GitHub available → `10-runtime-github.md`
   - GitHub unavailable → `11-runtime-inline.md`
3. **After Design System update** → ONE update prompt:
   - GitHub update → `20-update-github.md`
   - File upload → `21-update-inline.md`

---

## Important Rule

> If `CURRENT.md` is provided (via GitHub or inline),
> **no canonical or verbose prompt is required**.

---

**End of prompt/README.md**

