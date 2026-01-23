# RxCore Web Assets

This repository contains the **canonical runtime assets** required to run the
RxCore Web Viewer.

It is framework-agnostic and designed to support:
- documentation examples
- AI-generated integrations
- minimal and full-featured viewer deployments

The contents and structure of this repository are treated as **contractual** by
the RxCore documentation.

---

## Purpose

This repository answers one question:

> **What runtime assets must exist on disk for RxCore Web Viewer to initialize and run correctly?**

It provides:
- A canonical `/assets` runtime layout
- Supporting runtime files (scripts, fonts, HTML helpers, vendor folders)
- Minimal, authoritative documentation describing runtime expectations

It does **not** contain:
- Capability contracts (see `rxcore-capabilities`)
- Framework-specific code (Angular, React, build tooling)
- Full product or API documentation

---

## Documentation

Authoritative documentation for this repository is located under `docs/`:

- **`docs/project-structure.md`**  
  Canonical runtime folder layout and boot-time requirements.

- **`docs/rxconfig.md`**  
  Runtime configuration contract (`rxconfig.js`) and backend integration notes.

These documents are intentionally concise and are designed to be consumed by
both humans and AI agents.

---

## Relationship to other repositories

- **rxcore-capabilities**  
  Defines AI-first, machine-readable capability contracts
  (what RxCore can do and how it is invoked).

- **rxcore-web-assets** (this repository)  
  Defines the runtime assets required for those capabilities to function.

The two repositories are complementary and should be used together.

---

## Notes

- Some third-party dependencies (e.g. Foxit PDF SDK) may not be redistributable
  and must be supplied separately.
- While individual files may evolve, the overall asset structure is intended
  to remain stable.

---

## Status

This repository is used as a **canonical reference** for runtime setup in
documentation, examples, and AI-generated viewer integrations.
