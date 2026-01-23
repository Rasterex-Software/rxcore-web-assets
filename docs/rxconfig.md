# rxconfig.js

`rxconfig.js` defines the **runtime configuration contract** for RxCore Web Viewer.

It is evaluated early during viewer startup and provides environment-specific
settings that control backend interaction, document handling, and optional
server-assisted workflows.

This file is expected to exist at:
assets/scripts/rxconfig.js


and must be loaded **before** viewer initialization.

---

## Purpose

`rxconfig.js` is used to:

- Define backend endpoints used by RxCore
- Configure document loading and upload behavior
- Enable or disable server-assisted features
- Adapt the same runtime assets to different environments (dev, test, prod)

It is **not** a UI configuration file and does not define viewer layout,
markup tools, or feature behavior directly.

---

## Runtime expectations

At runtime, RxCore assumes that:

- `rxconfig.js` exists and is loadable
- The configuration object it defines is valid
- Required backend URLs are present if server-backed features are used

If required configuration values are missing or invalid, the viewer may fail
to initialize or certain workflows may not function.

---

## Typical contents

While the exact structure may vary by deployment, `rxconfig.js` commonly defines:

- Base API URLs
- Document service endpoints
- Upload and download routes
- Optional feature flags related to server interaction

A template file is often used as a starting point:



This template can be copied and adapted for each environment.

---

## Relationship to RxServer

When RxCore Web Viewer is used together with RxServer, `rxconfig.js` is also
responsible for configuring server-related behavior such as:

- Backend API endpoints
- Upload and document handling routes
- Server-assisted workflows

Detailed server-specific configuration options are documented separately in the
RxServer documentation:

https://docs.rasterex.com/docs/server/#rxconfigjs

This repository intentionally does **not** duplicate those details.
Instead, `rxconfig.js` is treated here as a **runtime configuration contract**
that may include server-related settings when applicable.

For AI-generated examples and minimal integrations, it is sufficient to:

- Provide valid backend endpoints
- Ensure `rxconfig.js` is loaded before viewer initialization

---

## Practical guidance

- Keep `rxconfig.js` environment-specific
- Do not hardcode deployment-specific values into other runtime files
- Treat `rxconfig.js` as the single source of truth for backend configuration

For example projects and documentation, placeholder values may be used as long
as they clearly indicate where real endpoints must be supplied.

---

## Summary

- `rxconfig.js` is required at boot time
- It defines backend and server interaction behavior
- It is environment-specific and deployment-dependent
- Detailed server options live in the RxServer documentation
- This repository documents the **contract**, not every possible configuration
