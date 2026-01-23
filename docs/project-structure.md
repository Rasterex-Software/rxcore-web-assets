# Canonical project structure

This repository provides the canonical runtime asset layout for RxCore Web Viewer.

All paths in documentation and code examples are assumed to be relative to the repository root, with runtime assets located under `assets/`.

## Folder layout

```text
assets/
├─ config/
│  └─ UIConfig.js            # Only required for web viewer can be dropped for barebone.
│
├─ fonts/                    # Fonts used for markup, signatures, and UI
│
├─ html/
│  └─ foxpage.html           # Required for Foxit PDF iframe integration
│
├─ images/                   # Icons and UI images (SVG, PNG, JPG)
│
├─ scripts/
│  ├─ rxcorefunctions.js     # RxCore runtime library (unminified)
│  ├─ rxcorefunctions.min.js # RxCore runtime library (minified)
│  ├─ rxconfig.js            # Active runtime configuration
│  ├─ rxconfig.template.js   # Configuration template for custom deployments
│  ├─ foxiframeconnect.js    # Foxit iframe bridge
│  ├─ jquery-2.1.0.min.js    # Required dependency
│  ├─ three.min.js           # Three.js for 3D support
│  ├─ GLTFLoader.js          # GLTF/GLB loader
│  ├─ BufferGeometryUtils.js
│  ├─ Detector.js
│  ├─ rxsignlibrary.js       # Signature support
│  └─ rxconstants.js         # Viewer constants (used by full web viewer)
│
├─ scss/
│  └─ config.scss            # Styles for full web viewer
│
└─ vendors/
   └─ foxit/
      └─ web/                # Foxit PDF SDK distribution

```

## Minimum required runtime (boot requirement)

Even if your application does not use PDF or 3D features, the viewer **may still require**
the baseline script and resource set described in the official “How to add to HTML” example.
In other words: a “logical minimal subset” is not always sufficient — if required baseline
dependencies are missing, RxCore may fail to initialize.

Use the “How to add to HTML” reference as the authoritative minimum boot-time dependency list:

https://docs.rasterex.com/docs/introduction/pro-version/getting-started/how-to-add-to-html

```html

    <script src="../assets/scripts/foxiframeconnect.js"></script>
    <script src="../assets/scripts/rxconfig.js"></script>
    <script src="../assets/scripts/rxcorefunctions.min.js"></script>
    <script type="text/javascript" src="../assets/scripts/three.min.js"></script>
    <script type="text/javascript" src="../assets/scripts/detector.js"></script>
    <script type="text/javascript" src="../assets/scripts/GLTFLoader.js"></script>
    <script type="text/javascript" src="../assets/scripts/jquery-2.1.0.min.js"></script>

```

Above the normally distributed rxcorefunctions.min.js is referenced this can sometimes be replaced by the non minified rxcorefunctions.js version.

### Practical rule

- If you want a viewer that reliably starts, include the full baseline from the reference above
  (including Three.js-related files and Foxit-related files), even if your current workflow does not use them.

## Feature usage subset (after boot)

Once the viewer is running, which features you actually *use* will determine what runtime
components matter operationally (e.g. Foxit callbacks, 3D loaders, signature fonts, etc.).

## Notes

- Git tracks folders only if they contain files; use `.keep` placeholders where needed.
- Some third-party dependencies (e.g. Foxit SDK) may not be redistributable and must be added separately.


