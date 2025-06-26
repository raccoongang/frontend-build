# @openedx/frontend-build with Overrides Support

This is a customized version of `@openedx/frontend-build` with built-in support for Micro Frontend (MFE) component overrides.  
Overrides are bundled **inside this package** in the `overrides/` directory.

---

## Directory Structure

```plaintext
@openedx/frontend-build/
├── lib/
├── config/
├── overrides/
│   └── frontend-app-<name>/
│       └── src/
│           └── components/
│               └── Banner.jsx
└── package.json
```

## Tutor Integration

If you’re using tutor-contrib-rg-theme, the plugin uses the RG_FRONTEND_BUILD override key in the MFES_OVERRIDES_MAP inside constants.py:

```python
DEFAULT_MFE_OVERRIDES_WITH_BUILD = [
    RG_THEME_BRAND,
    RG_THEME_HEADER,
    RG_THEME_FOOTER,
    RG_FRONTEND_BUILD,
]

MFES_OVERRIDES_MAP = {
    "profile": DEFAULT_MFE_OVERRIDES_WITH_BUILD,
    ...
}
```
Tutor mounts the appropriate override folder (e.g., overrides/frontend-app-profile) from this package into the container at build time.
