# Inventory

**Version:** 0.1.0
**Date:** 2026-11-22

## Root Files

| File | Purpose | Status |
|------|---------|--------|
| `README.md` | Project overview and current state | ✅ |
| `STATUS.md` | Precise current state | ✅ |
| `CHANGELOG.md` | Change history | ✅ |
| `AUTHORS.md` | Authorship | ✅ |
| `CONTRIBUTING.md` | Contribution policy | ✅ |
| `INVENTORY.md` | This file | ✅ |
| `CITATION.cff` | Citation metadata | ✅ |
| `VERSION` | 0.1.0 | ✅ |
| `LICENSE` | CC-BY-4.0 | ✅ |
| `scientific_state.json` | Official state record | ✅ |
| `manifest.json` | Machine-readable metadata | ✅ |

## RESEARCH/

| File | Purpose | Status |
|------|---------|--------|
| `BOUNDARY_INVESTIGATION.md` | Core investigation document | ✅ AUTHOR DECLARED |
| `ARCHITECTURAL_HYPOTHESIS.md` | Documented absence (Phase 0 not authorized) | ✅ |

## FALSIFICATION/

| File | Purpose | Status |
|------|---------|--------|
| `HRT-01_REPRESENTATIONAL_TEST.md` | Representational test for H1–H5 | 🟡 PENDING |
| `HRT-01_MAINTENANCE_TEST.md` | Maintenance test for H1–H5 | 🟡 PENDING |
| `HRT-02_COMPOSITIONAL_SYNCHRONIZATION_TEST.md` | Compositional synchronization test | 🟡 PENDING |
| `HRT-02_COMPOSITION_ANALYSIS.md` | Composition analysis | 🟡 PENDING |

## REVIEW/

| File | Purpose | Status |
|------|---------|--------|
| `INDEPENDENT_REVIEW_PROTOCOL.md` | Pre-review protocol | ✅ |
| `INDEPENDENT_REVIEW.md` | Completed external review by Jonathan Rabe (2026-11-22) | ✅ COMPLETED |

## paper/

| File | Purpose | Status |
|------|---------|--------|
| `AetherHarness_Research_Paper_v0.1.0.md` | Full research paper (Markdown source) | ✅ |
| `AetherHarness_Research_Paper_v0.1.0.pdf` | Full research paper (PDF, 34 pages) | ✅ |
| `convert_to_pdf.py` | PDF generation script (WeasyPrint) | ✅ |

**Paper contents:**
- Title page + Abstract + 12 sections
- 4 figures (from `docs/figures/`)
- 7 tables
- 30 references
- 3 appendices (A: Aether family, B: Glossary, C: Change log)
- Status: (E) Undetermined

## docs/figures/

| File | Purpose | Dimensions |
|------|---------|------------|
| `Fig1_Status_Taxonomy.png` | Status taxonomy: EXTERNALLY REVIEWED, HRT Pending, Phase 0 Not Authorized | 1408×768 |
| `Fig2_Overlap_Matrix.png` | Overlap matrix: H1–H5 responsibilities vs. Aether dimensions | 1344×756 |
| `Fig3_Investigation_Flow.png` | Investigation flow: BOUNDARY → HRT-01/02 → Composition → External Review | 1408×768 |
| `Fig4_Five_Responsibilities.png` | The five candidate responsibilities (H1–H5) | 1408×768 |

## Not included (by design)

- No implementation.
- No code (other than `convert_to_pdf.py`, which is a utility script, not an implementation of AetherHarness).
- No experiments.
- No architectural hypothesis (Phase 0 not authorized).
- No publication.
- No roadmap.

## Totals

- Root: 11 files
- RESEARCH/: 2 files
- FALSIFICATION/: 4 files
- REVIEW/: 2 files
- paper/: 3 files
- docs/figures/: 4 files
- **Total: 26 files**

**Status:** EXTERNALLY REVIEWED (recommendation (a)),
Phase 0 NOT AUTHORIZED, Decision (E) Undetermined
