# AetherHarness — Independent Review Protocol

**Status:** Boundary Investigation — Pre-Review Protocol
**Version:** 0.1.0
**Date:** 2026-11-22
**Author:** Samir Baladi
**License:** CC-BY-4.0

---

## 0. Purpose

This protocol states how an independent review of AetherHarness should be
conducted. It is written **before** the review, so that the review cannot be
shaped after the fact by its outcome.

The protocol does **not** presuppose the outcome. A review that concludes
"the current state (DRAFT, Remainder Candidate, Phase 0 Not Authorized) is
correct" and a review that concludes "the investigation is incomplete or
overstated" are both valid outcomes.

---

## 1. Independence requirement

The reviewer must be independent of the author. Independence means:

- the reviewer is not the author;
- the reviewer has not contributed to the boundary investigation, the
  falsification tests, or the composition analysis;
- the reviewer has no stake in the outcome of the investigation;
- the reviewer has no stake in the outcome of any of the Aether dimensions
  (AetherHuman, AetherGovern, AetherPolicy, AetherRuntime, AetherAudit,
  AetherOrchestrate) that could bias the assessment of overlaps.

The reviewer declares independence in `INDEPENDENT_REVIEW.md` (Section 1.1).

---

## 2. Artifacts to be reviewed

The reviewer reads, in order:

1. `README.md` — project overview and current state.
2. `STATUS.md` — precise current state.
3. `RESEARCH/BOUNDARY_INVESTIGATION.md` — the core investigation document.
4. `FALSIFICATION/HRT-01_REPRESENTATIONAL_TEST.md` — representational test.
5. `FALSIFICATION/HRT-01_MAINTENANCE_TEST.md` — maintenance test.
6. `FALSIFICATION/HRT-02_COMPOSITIONAL_SYNCHRONIZATION_TEST.md` —
   compositional synchronization test.
7. `FALSIFICATION/HRT-02_COMPOSITION_ANALYSIS.md` — composition analysis.
8. `ARCHITECTURAL_HYPOTHESIS.md` — documented absence (Phase 0 not authorized).

The reviewer may read any other artifact in the repository. The eight above
are the minimum.

---

## 3. Questions the review must answer

### 3.1 On the boundary investigation

- **B1.** Does `RESEARCH/BOUNDARY_INVESTIGATION.md` correctly identify the overlaps
  between AetherHarness's candidate responsibilities (H1–H5) and existing
  Aether dimensions?
- **B2.** Is AetherHuman treated fairly as the most consequential overlap,
  or is its scope understated or overstated?
- **B3.** Is AetherGovern treated fairly as the second most consequential
  overlap?
- **B4.** Are the risks of collapse (H1–H5 collapsing into existing
  dimensions) honestly recorded, or are they softened?

### 3.2 On the falsification tests

- **R1.** Does HRT-01 (representational test) actually test whether H1–H5 are
  architectural rather than operational?
- **R2.** Does HRT-01 (maintenance test) distinguish maintenance across
  workflows from a single-step specification?
- **R3.** Does HRT-02 (compositional synchronization test) examine
  composition, or only individual dimensions?
- **R4.** Does HRT-02 (composition analysis) reach "Insufficient Evidence"
  honestly, or does it prematurely conclude?

### 3.3 On the state and claims

- **S1.** Is the synchronization remainder correctly classified as
  **Candidate** (not confirmed, not dismissed)?
- **S2.** Is AetherHarness independence correctly classified as
  **Undetermined**?
- **S3.** Is Phase 0 correctly classified as **NOT AUTHORIZED**?
- **S4.** Is any claim in `README.md`, `STATUS.md`, or
  `RESEARCH/BOUNDARY_INVESTIGATION.md` stated more strongly than the evidence supports?

### 3.4 On the documentation

- **D1.** Are `scientific_state.json`, `manifest.json`, `README.md`,
  `STATUS.md`, and `RESEARCH/BOUNDARY_INVESTIGATION.md` internally consistent?
- **D2.** Does `ARCHITECTURAL_HYPOTHESIS.md` correctly document the absence
  of a hypothesis (rather than being an empty placeholder)?
- **D3.** Is the decision (E) Undetermined the correct classification given
  the evidence?

---

## 4. Format of the review

The reviewer completes `INDEPENDENT_REVIEW.md` with:

1. **Reviewer identity and independence declaration.**
2. **Artifacts reviewed** (checklist against Section 2).
3. **Answers to B1–B4, R1–R4, S1–S4, D1–D3.**
4. **A recommendation**, one of:
   - (a) confirm the current state (DRAFT, Remainder Candidate, Phase 0 Not Authorized);
   - (b) recommend revision of one or more artifacts before final state;
   - (c) recommend a change of state (with reasons).
5. **A statement of what the reviewer did not review.**

---

## 5. What the review is not

- It is not a peer review for publication.
- It is not an implementation review.
- It is not authorization for Phase 0.
- It is not binding on the author, but the final state of the investigation
  must record why it departs from the review's recommendation (if it does).

---

## 6. Conflict of interest

A reviewer with a conflict of interest (for example, a stake in AetherHuman,
AetherGovern, AetherPolicy, AetherRuntime, AetherAudit, or AetherOrchestrate)
must declare it. A declared conflict does not automatically disqualify the
reviewer, but it is recorded in `INDEPENDENT_REVIEW.md`.

---

## 7. Timeline

| Step | Action | Owner |
|------|--------|-------|
| 1 | Author declares the investigation ready for review | Author |
| 2 | Reviewer receives this protocol and the artifacts in Section 2 | Author → Reviewer |
| 3 | Reviewer completes `INDEPENDENT_REVIEW.md` | Reviewer |
| 4 | Author records the review and updates the state | Author |
| 5 | If (b) or (c): revision cycle | Author |
| 6 | Final state recorded in `scientific_state.json` and `STATUS.md` | Author |

---

**AetherHarness v0.1.0 — Independent Review Protocol**
© 2026 Samir Baladi — Ronin Institute / Rite of Renaissance
DOI: 10.5281/zenodo.24425655
