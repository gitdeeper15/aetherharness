# AetherHarness — Boundary Investigation

**Status:** 🟡 DRAFT — NOT REVIEWED, NOT SIGNED
**Date:** 2026-11-21
**Author:** Samir Baladi (with AI assistance)

---

## 0. Purpose

This document records the boundary investigation that must precede any Phase 0 claim for AetherHarness. It identifies the overlaps with existing Aether dimensions, with particular attention to **AetherHuman** (the most consequential overlap) and **AetherGovern** (the second most consequential).

The investigation does not conclude that AetherHarness is or is not independent. It records the overlaps, the risks of collapse, and the questions that HRT-01 must answer.

---

## 1. The Overlap with AetherHuman

### 1.1 Why AetherHuman Is the Most Consequential Overlap

The source report uses two concepts that intersect directly with AetherHuman:
- **Decision Rights** — who decides what, within a workflow.
- **Bounded Autonomy** — how much independence an agent has, within defined limits.

If AetherHuman already covers "who decides what" and "how much autonomy an agent has," then AetherHarness's H5 (Workflow Decision Rights) may be a **restatement** of AetherHuman, not a new responsibility.

### 1.2 What AetherHuman Covers (Author's Reading)

AetherHuman is candidate #11. Its territory, as the author reads it, is:
- Human oversight of autonomous agents.
- Human intervention in agent workflows.
- Human decision rights (who decides what).
- Bounded autonomy (how much independence an agent has).

**Note.** This is the author's reading, not a verified specification. If AetherHuman's territory is narrower (e.g., only "intervention" and not "decision rights"), then the overlap is smaller.

### 1.3 What AetherHarness's H5 Covers

H5 (Workflow Decision Rights) covers:
- The **distribution** of decision rights between human and agent.
- The **maintenance** of that distribution across a multi-step workflow.
- The **drift** of decision rights as the workflow evolves.

### 1.4 The Distinction (If Any)

The distinction between AetherHuman and AetherHarness's H5 is **temporal**:
- AetherHuman specifies **who** has decision rights.
- AetherHarness's H5 specifies **how decision rights are maintained** across a multi-step workflow, including drift.

Whether this distinction is architectural (a separate responsibility) or operational (a use of AetherHuman's specification) is the central question of HRT-01.

### 1.5 The Risk of Collapse

If AetherHuman's specification is later expanded to include "maintenance of decision rights across workflows," then H5 collapses into AetherHuman. If it is not, H5 may be a genuine remainder.

**This is not resolved here.** It is recorded as a risk.

---

## 2. The Overlap with AetherGovern

### 2.1 Why AetherGovern Is the Second Most Consequential Overlap

AetherGovern covers **authority and delegation**. AetherHarness's H1 (Access Governance) and H2 (Action Governance) both involve **authority** (who may access, who may act). If AetherGovern already covers "who may access" and "who may act," then H1 and H2 may be restatements of AetherGovern.

### 2.2 What AetherGovern Covers (Author's Reading)

- Authority (who may do what).
- Delegation (how authority is passed).
- Revocation (how authority is withdrawn).
- Scope (what the authority covers).

**Note.** This is the author's reading, not a verified specification.

### 2.3 What AetherHarness's H1 and H2 Cover

- **H1 (Access Governance):** control over what the agent can see and reach.
- **H2 (Action Governance):** control over what the agent is allowed to do.

### 2.4 The Distinction (If Any)

The distinction between AetherGovern and AetherHarness's H1/H2 is **operational**:
- AetherGovern specifies **authority** (who may do what).
- AetherHarness's H1/H2 specify **operational control** (what the agent can see, what it can do, as the workflow evolves).

Whether this distinction is architectural or merely a use of AetherGovern's specification is the central question of HRT-01.

### 2.5 The Risk of Collapse

If AetherGovern's specification is later expanded to include "operational control across workflows," then H1 and H2 collapse into AetherGovern. If it is not, H1 and H2 may be genuine remainders.

**This is not resolved here.** It is recorded as a risk.

---

## 3. The Overlaps with AetherPolicy, AetherRuntime, AetherAudit, and AetherOrchestrate

### 3.1 AetherPolicy

Covers rules and enforcement. H3 (Execution Guardrails) and H2 (Action Governance) both involve rules. The distinction (if any) is **operational** (maintenance across workflows) versus **specification** (what the rules are).

### 3.2 AetherRuntime

Covers execution monitoring and assurance. H3 (Execution Guardrails) and H4 (Feedback Loops) both involve runtime. The distinction (if any) is **integration** (maintaining all responsibilities together) versus **execution** (monitoring and assurance).

### 3.3 AetherAudit

Covers records and evidence. H4 (Feedback Loops) and H5 (Decision Rights) both involve records. The distinction (if any) is **feedforward** (using records to change behavior) versus **recording** (capturing what happened).

### 3.4 AetherOrchestrate

Covers workflow coordination. H4 (Feedback Loops) and H5 (Decision Rights) both involve workflow. The distinction (if any) is **decision rights** (who decides) versus **task assignment** (who does what).

---

## 4. The Central Question of HRT-01

The central question is not "does each responsibility have an existing home?" (the preliminary answer is yes, but with reservations).

The central question is:

> **Is the integrated maintenance of the harness — across all five responsibilities, simultaneously, as the workflow evolves — a remainder that the six existing dimensions cannot cover?**

If yes, AetherHarness may proceed to Phase 0.
If no, AetherHarness is documented as a negative result.

---

## 5. What This Document Does Not Claim

- That AetherHarness is independent.
- That AetherHuman, AetherGovern, or any other dimension is insufficient.
- That the boundaries recorded here are final. They are the author's reading, and they may change if the underlying specifications change.

---

**DRAFT — NOT REVIEWED, NOT SIGNED**
**Author:** Samir Baladi (with AI assistance)
**Date:** 2026-11-21

---

## Author Declaration

I confirm that the contents of this document accurately reflect the
investigation conducted, that the conclusions are provisional and contingent
on review, and that no claim of a confirmed synchronization remainder, an
independent architectural layer, or authorization of Phase 0 is made.

**Author:** Samir Baladi
**Affiliation:** Ronin Institute / Rite of Renaissance
**ORCID:** 0009-0003-8903-0029
**Date:** 2026-11-22
**Signature:** ______________________

**Status of this document:** AUTHOR DECLARED — AWAITING EXTERNAL REVIEW
