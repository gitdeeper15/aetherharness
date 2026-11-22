# HRT-01 — Integrated Maintenance Test

**Status:** 🟡 DRAFT — NOT REVIEWED, NOT SIGNED
**Date:** 2026-11-21
**Author:** Samir Baladi (with AI assistance)
**Reviewer:** _(to be assigned)_
**Verdict:** PENDING

---

## 0. The Question

> Can the integrated maintenance of the harness — across all five responsibilities, simultaneously, as the workflow evolves — be covered by the six existing dimensions without introducing an additional architectural primitive?

This test is the decisive part of HRT-01. The Representation Matrix (see `HRT-01_REPRESENTATIONAL_TEST.md`) found that each responsibility has an existing home, but with **maintenance reservations** (drift, scope creep, guardrail drift, loop integrity, decision-right drift).

This test asks whether those reservations **survive integration** — that is, whether the six dimensions, composed, can maintain all five responsibilities simultaneously across a multi-step workflow.

---

## 1. The Test Scenario

We use a single multi-step workflow with **three tasks**, in which the context, tools, and parties change.

### Workflow: "Supplier Onboarding and Purchase"

| Step | Task | Context change | Tools used | Parties involved |
|:-:|---|---|---|---|
| **T1** | Identify preferred suppliers | Market data access | Search tool, directory API | Agent, human (delegator) |
| **T2** | Request quotes from shortlisted suppliers | Supplier portals | Email tool, portal API | Agent, human, 3 suppliers |
| **T3** | Place order with chosen supplier | Payment gateway | Payment API, audit log | Agent, human, supplier, bank |

**What must be maintained simultaneously at each step:**
- **H1 (Access Governance):** the agent can only see and reach what its delegation permits.
- **H2 (Action Governance):** the agent can only do what its delegation permits.
- **H3 (Execution Guardrails):** constraints (budget, rate, forbidden sequences) are enforced.
- **H4 (Feedback Loops):** outcomes feed back into review.
- **H5 (Workflow Decision Rights):** decision rights (who approves what) are respected.

---

## 2. Step-by-Step Analysis

### Step T1 — Identify Preferred Suppliers

**Context:** The agent is given access to market data and a directory API.

**Maintenance questions:**
- **H1 (Access):** Does the agent's access to market data persist into T2? If not, is the revocation immediate? → Govern + Policy can specify; Runtime can enforce.
- **H2 (Action):** Does the agent have authority to search, but not to request quotes yet? → Govern can scope; Policy can gate.
- **H3 (Guardrails):** Are search rate limits enforced? → Policy + Runtime can enforce.
- **H4 (Feedback):** Does the list of suppliers feed into T2? → Runtime + Audit can record; Human reviews.
- **H5 (Decision Rights):** Who approves the shortlist? → Govern + Human can specify.

**Result for T1:** All five responsibilities are covered by the composition. ✓ (no remainder at this step).

---

### Step T2 — Request Quotes

**Context:** The agent now has access to supplier portals and email tools. Parties change (suppliers are now involved).

**Maintenance questions:**
- **H1 (Access):** The agent's access to market data (from T1) should now be **revoked** or **restricted**. Is that maintained? → Govern can revoke; Policy can update; Runtime can enforce. **But who decides when to revoke?** → Human (H5). **Is the revocation synchronized with the context change?** → Orchestrate.
- **H2 (Action):** The agent can now send emails and use portals, but not yet place orders. Is the scope change enforced? → Policy can update; Govern can re-authorize.
- **H3 (Guardrails):** Rate limits on emails (to avoid spam) must be enforced. → Policy + Runtime.
- **H4 (Feedback):** Supplier responses feed back into the decision. → Runtime + Audit; Human reviews.
- **H5 (Decision Rights):** Who approves the quotes? → Govern + Human.

**Result for T2:** All five are covered in principle. **But** there is a **synchronization question**: when the context changes (T1 → T2), the agent's authority must be updated. Who coordinates this? Govern specifies, Policy enforces, but **the coordination of the update across all five responsibilities** is not obviously covered by any single dimension.

**Is this a remainder?** → **To be determined.** It may be an application of AetherOrchestrate (workflow coordination) or an application of AetherHuman (human oversight).

---

### Step T3 — Place Order

**Context:** The agent now has access to the payment gateway. Parties change again (bank, supplier).

**Maintenance questions:**
- **H1 (Access):** Access to supplier portals should be revoked (or restricted). → Govern + Policy + Runtime.
- **H2 (Action):** The agent can now place orders, but only within budget. Is the scope enforced? → Policy.
- **H3 (Guardrails):** Payment limits and forbidden sequences enforced. → Policy + Runtime.
- **H4 (Feedback):** The outcome feeds back into audit and future decisions. → Audit + Human.
- **H5 (Decision Rights):** Who approves the order? → Govern + Human.

**Result for T3:** All five are covered in principle. **But** the same **synchronization question** arises: as the workflow moves from T2 to T3, the agent's authority and guardrails must be updated together, or an inconsistency may arise (e.g., the agent still has access to supplier portals but is now placing an order through the payment gateway — a potential security gap).

**Is this a remainder?** → **To be determined.**

---

## 3. The Synchronization Question

Across T1 → T2 → T3, the **synchronization of updates** across all five responsibilities is the central question. This is the "remainder" candidate.

**Candidate framings:**

1. **Framing A — AetherOrchestrate covers synchronization.** If Orchestrate is responsible for coordinating workflow transitions, then synchronization is an application of Orchestrate.

2. **Framing B — AetherHuman covers synchronization.** If Human is responsible for oversight at each transition, then synchronization is an application of Human.

3. **Framing C — Neither covers synchronization.** If both Orchestrate and Human are silent on how updates propagate across responsibilities, then synchronization is a genuine remainder.

**This test does not resolve the question.** It records it as the central question of HRT-01.

---

## 4. The Decision

**Verdict: PENDING.**

The Integrated Maintenance Test finds that:
- Each responsibility is covered at each step (Representation Matrix confirmed).
- The **synchronization of updates** across responsibilities is the remainder candidate.
- It is not yet clear whether this synchronization is covered by Orchestrate, by Human, or by neither.

**The remainder is real if and only if:**
- AetherOrchestrate does not cover synchronization, AND
- AetherHuman does not cover synchronization, AND
- No composition of the other four covers it.

**This requires a closer reading of AetherOrchestrate and AetherHuman.** It is the next step.

---

## 5. Next Step

1. Examine AetherOrchestrate: does its specification cover synchronization of updates across responsibilities?
2. Examine AetherHuman: does its specification cover synchronization of updates across responsibilities?
3. If both are silent: the remainder is real. AetherHarness may proceed to Phase 0.
4. If either covers it: the remainder is not real. AetherHarness is documented as a negative result.

---

**DRAFT — NOT REVIEWED, NOT SIGNED**
**Author:** Samir Baladi (with AI assistance)
**Date:** 2026-11-21
