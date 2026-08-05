# BrainChip Akida 2 Developer Course

Self-contained HTML training material covering BrainChip's Akida 2 neuromorphic
IP — from core architecture through quantization, model conversion, device
mapping, and on-hardware inference and performance measurement.

## Viewing the course

Each module is a single, self-contained HTML file (styles, scripts, and images
all inlined) — no build step or server required. Open
[`Akida/akida_module1.html`](Akida/akida_module1.html) in a browser and
navigate forward using the sidebar or the bottom-of-page controls.

## Structure

| File | Module | Covers |
|---|---|---|
| [`akida_module1.html`](Akida/akida_module1.html) | 1 — What is Akida 2? | Event-based processing, sparsity, at-memory compute, product family |
| [`akida_module2.html`](Akida/akida_module2.html) | 2 — Hardware Architecture | Node mesh, NPEs, component types (HRC/CNP/FNP/TNP), memory hierarchy, DMA |
| [`akida_module3.html`](Akida/akida_module3.html) | 3 — Quantization | Scale/zero-point mechanics, calibration, PTQ vs QAT, bitwidth selection |
| [`akida_module4.html`](Akida/akida_module4.html) | 4 — MetaTF Flow | Keras → `quantizeml` → `cnn2snn` → Akida pipeline |
| [`akida_module5.html`](Akida/akida_module5.html) | 5 — MetaONNX Flow | ONNX → `onnx2akida.convert()` → HybridModel pipeline |
| [`akida_module6.html`](Akida/akida_module6.html) | 6 — Devices & Mapping | Virtual/real devices, `create_device()`, MapMode, `model.summary()` |
| [`akida_module7.html`](Akida/akida_module7.html) | 7 — Inference & Performance | `forward()`/`predict()`, FPS/power statistics, CLI, Akida Cloud, optimization |

Supplementary / not part of the main sequence:

- [`qat_explainer.html`](Akida/qat_explainer.html) — standalone deep-dive on how QAT works, not linked from the module sidebar/nav.
- `Tenns/` — reserved for upcoming TENNs-focused modules (not yet added).

## Review status

Modules 1–7 have been through a technical accuracy pass reconciling course
content against BrainChip SME feedback and internal consistency checks
(hardware capability claims, quantization scheme details, dangling
cross-references, etc.). A handful of points are intentionally worded as
pending rather than asserted as fact, and are called out inline with
"— confirming with the HW/SW team" (or similar) where the exact behavior
wasn't certain at review time — e.g. the precise CNP1 vs CNP2 selection
criteria, and the exact effect of `onnx2akida.convert()`'s `enable_hwpr`
argument. Search the modules for "HW/SW team" to find all such flags.

## Contributing

These pages carry Marketing-approved formatting and branding — edits should
be **content-only**: fix or update text, tables, and inline diagram data
without changing HTML structure, CSS, or layout. When a technical claim can't
be confirmed with confidence, soften the wording and flag it inline rather
than asserting or deleting it outright.
