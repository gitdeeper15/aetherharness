# HRT-01 — Harness Representational Test

**Status:** 🟡 DRAFT — NOT REVIEWED, NOT SIGNED
**Date:** 2026-11-21
**Author:** Samir Baladi (with AI assistance)
**Reviewer:** _(to be assigned)_
**Verdict:** PENDING

---

## 0. The Question

> Can the complete operational harness of an autonomous agent be represented and maintained through the existing Aether dimensions — including action constraints, execution guardrails, tool boundaries, feedback loops, and human decision rights — without introducing an additional architectural primitive?

**What "harness" means here.** The integrated operational environment in which an agent acts: what it can see, what it can do, what it can use, how its actions are constrained during execution, how results feed back, and who holds decision rights.

**What "represent" means.** For each responsibility of the harness, identify whether at least one existing Aether dimension provides the mechanism to specify, enforce, or record it.

**What "maintain" means.** For each responsibility, identify whether the existing dimensions can preserve it across a multi-step workflow, including changes in context, tools, and parties.

---

## 1. The Five Harness Responsibilities

From the source report (see `RESEARCH/BOUNDARY_INVESTIGATION.md`):

| ID | Responsibility | What it covers |
|:-:|---|---|
| **H1** | Access Governance | What the agent can see and reach |
| **H2** | Action Governance | What the agent is allowed to do |
| **H3** | Execution Guardrails | Constraints enforced during execution |
| **H4** | Feedback Loops | Feeding outcomes back into review and improvement |
| **H5** | Workflow Decision Rights | Distribution of decision rights between human and agent |

---

## 2. The Six Existing Dimensions

| ID | Dimension | What it covers (author's reading) |
|:-:|---|---|
| **D1** | AetherGovern | Authority, delegation, revocation |
| **D2** | AetherPolicy | Rules, conditions, enforcement |
| **D3** | AetherRuntime | Execution monitoring, assurance |
| **D4** | AetherAudit | Records, evidence, accountability |
| **D5** | AetherOrchestrate | Workflow, coordination, task assignment |
| **D6** | AetherHuman | Human oversight, intervention, decision rights |

**Note.** These are the author's readings, not verified specifications. The test is conditional on these readings. If a dimension is later shown to cover more (or less) than stated here, the result of HRT-01 may change.

---

## 3. The Representation Matrix (Preliminary)

For each harness responsibility, we ask: can it be represented by the six dimensions?

| Responsibility | Govern | Policy | Runtime | Audit | Orchestrate | Human | Remainder? |
|---|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| **H1** Access Governance | ? | ? | ? | ? | ? | ? | ? |
| **H2** Action Governance | ? | ? | ? | ? | ? | ? | ? |
| **H3** Execution Guardrails | ? | ? | ? | ? | ? | ? | ? |
| **H4** Feedback Loops | ? | ? | ? | ? | ? | ? | ? |
| **H5** Workflow Decision Rights | ? | ? | ? | ? | ? | ? | ? |

**Legend:** ✓ = full coverage; ◐ = partial coverage; ✗ = no coverage; ? = to be determined.

---

## 4. Test Procedure

For each responsibility (H1–H5):

1. **Specify the requirement.** What must the harness provide?
2. **Check each dimension.** Does the dimension provide the mechanism?
3. **Check the composition.** Can the six dimensions together provide the mechanism?
4. **Check the maintenance.** Can the mechanism survive a multi-step workflow?
5. **Record the result.** ✓, ◐, ✗, or ?.
6. **Identify the remainder.** If no composition provides the mechanism, the remainder is real.

---

## 5. Preliminary Analysis (To Be Completed)

### H1 — Access Governance

**Requirement:** Control what the agent can see and reach (data, tools, other agents, environment).

**Dimension check:**
- **AetherGovern:** Can grant/revoke access authority. ✓ for authority.
- **AetherPolicy:** Can specify access conditions (e.g., "only trusted suppliers"). ✓ for rules.
- **AetherRuntime:** Monitors what the agent accesses. ◐ for detection.
- **AetherAudit:** Records what the agent accessed. ◐ for evidence.
- **AetherOrchestrate:** Assigns tasks but does not gate access. ✗.
- **AetherHuman:** Can intervene but does not provide continuous access control. ✗.

**Composition:** Govern + Policy + Runtime + Audit can specify, enforce, and record access. ✓.

**Maintenance:** Can this survive a multi-step workflow? The concern is **context drift**: access granted for one task may persist (or be revoked) incorrectly as the workflow moves between tasks. Whether this is a harness problem or a Govern/Policy problem is the central question of HRT-01.

**Preliminary result for H1:** ✓ (covered by composition), with a reservation about context drift.

---

### H2 — Action Governance

**Requirement:** Control what the agent is allowed to do (transaction types, tool calls, side effects).

**Dimension check:**
- **AetherGovern:** Authority to act. ✓.
- **AetherPolicy:** Rules about what may be done. ✓.
- **AetherRuntime:** Detects violations during execution. ◐.
- **AetherAudit:** Records actions. ◐.
- **AetherOrchestrate:** Assigns tasks, but does not gate actions. ✗.
- **AetherHuman:** Can intervene, but does not provide continuous control. ✗.

**Composition:** Govern + Policy + Runtime can specify and enforce action boundaries. ✓.

**Maintenance:** The concern is **scope creep**: an agent authorized for one action may be implicitly authorized for adjacent actions. This is a known problem (confused deputy; capability systems). Whether it is a harness problem or a Govern problem is open.

**Preliminary result for H2:** ✓ (covered by composition), with a reservation about scope creep.

---

### H3 — Execution Guardrails

**Requirement:** Enforce constraints during execution (e.g., rate limits, resource caps, forbidden sequences).

**Dimension check:**
- **AetherGovern:** Sets authority but not runtime constraints. ✗.
- **AetherPolicy:** Can specify runtime constraints as rules. ✓.
- **AetherRuntime:** Enforces constraints during execution. ✓.
- **AetherAudit:** Records execution. ◐.
- **AetherOrchestrate:** Coordinates workflow but does not enforce guardrails. ✗.
- **AetherHuman:** Can intervene, but not continuously. ✗.

**Composition:** Policy + Runtime can specify and enforce guardrails. ✓.

**Maintenance:** The concern is **guardrail drift**: constraints appropriate for one task may be inappropriate for the next. Whether this is a harness problem or a Policy problem is open.

**Preliminary result for H3:** ✓ (covered by composition), with a reservation about guardrail drift.

---

### H4 — Feedback Loops

**Requirement:** Feed outcomes back into review and improvement.

**Dimension check:**
- **AetherGovern:** Can use feedback to change authority. ◐.
- **AetherPolicy:** Can use feedback to update rules. ◐.
- **AetherRuntime:** Produces feedback (events, alerts). ✓.
- **AetherAudit:** Records feedback as evidence. ✓.
- **AetherOrchestrate:** Can route feedback to the next task. ◐.
- **AetherHuman:** Reviews and decides. ✓.

**Composition:** Runtime + Audit + Human can produce, record, and act on feedback. ✓.

**Maintenance:** The concern is **feedback loop integrity**: whether the feedback actually reaches the decision-maker and is acted upon. Whether this is a harness problem or an Audit/Human problem is open.

**Preliminary result for H4:** ✓ (covered by composition), with a reservation about loop integrity.

---

### H5 — Workflow Decision Rights

**Requirement:** Distribute decision rights between human and agent across a workflow.

**Dimension check:**
- **AetherGovern:** Defines who has authority. ✓.
- **AetherPolicy:** Defines conditions for delegation. ✓.
- **AetherRuntime:** Enforces the current decision rights. ◐.
- **AetherAudit:** Records who decided what. ✓.
- **AetherOrchestrate:** Assigns tasks but does not define decision rights. ✗.
- **AetherHuman:** Exercises decision rights. ✓.

**Composition:** Govern + Policy + Human can define and exercise decision rights. ✓.

**Maintenance:** The concern is **decision-right drift**: as workflows evolve, decision rights may shift implicitly, without explicit re-authorization. Whether this is a harness problem or a Govern problem is open.

**Preliminary result for H5:** ✓ (covered by composition), with a reservation about decision-right drift.

---

## 6. Preliminary Verdict

**Verdict: PENDING.** The preliminary analysis finds no explicit remainder: every harness responsibility is covered by at least one composition of the six dimensions.

**However**, each responsibility carries a **maintenance reservation**: a type of drift (context drift, scope creep, guardrail drift, loop integrity, decision-right drift) that may not be fully covered.

**The central question of HRT-01** is therefore not "is each responsibility covered?" (the preliminary answer is yes) but "**is the integrated maintenance of the harness covered?**"

This is the remainder that must be tested.

---

## 7. Next Step

The next step is to test the **integrated maintenance** of the harness: a multi-step workflow in which all five responsibilities must be maintained simultaneously, across changes in context, tools, and parties.

If the integrated maintenance is covered, AetherHarness is not a separate dimension.
If it is not covered, AetherHarness may proceed to Phase 0.

---

**DRAFT — NOT REVIEWED, NOT SIGNED**
**Author:** Samir Baladi (with AI assistance)
**Date:** 2026-11-21
