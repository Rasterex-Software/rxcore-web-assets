# Rasterex Web SDK – Runtime Assets

This repository contains the **canonical runtime assets** required to run a
minimal implementation of the **Rasterex Web SDK**.

It is framework-agnostic and intended for:
- minimal, custom integrations
- documentation examples
- AI-generated SDK usage
- environments that do not use the Angular-based Web Viewer

The contents and structure of this repository are treated as **contractual**
by the Rasterex SDK documentation.

---

## Purpose

This repository answers one question:

> **What runtime assets must exist on disk for the Rasterex Web SDK to initialize and run correctly?**

It provides:
- A canonical `/assets` runtime layout
- Supporting runtime files (scripts, fonts, HTML helpers, vendor folders)
- Minimal, authoritative documentation describing boot-time expectations

It does **not** contain:
- Framework-specific implementations (Angular, React, build tooling)
- UI application logic
- Capability contracts (see `rxcore-capabilities`)
- The Angular-based Rasterex Web Viewer

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

## Relationship to other projects

- **rxcore-capabilities**  
  Defines AI-first, machine-readable capability contracts
  (what the Rasterex Web SDK can do and how it is invoked).

- **Angular Web Viewer (separate project)**  
  A full-featured application built on top of the Rasterex Web SDK.
  It has its own repository, build system, and asset pipeline.

- **This repository**  
  Defines the **minimum runtime asset baseline** required by the Rasterex Web SDK,
  independent of any application framework.

---

## Notes

- Some third-party dependencies (e.g. Foxit PDF SDK) may not be redistributable
  and must be supplied separately.
- While individual files may evolve, the overall asset structure is intended
  to remain stable.

---

## Status

This repository is used as a **canonical reference** for minimal runtime setup
in documentation, examples, and AI-generated Rasterex Web SDK integrations.
