# Product Requirements Document (PRD)

## Purpose and Guidelines

This template helps teams think through the purpose, goals, and implications of product ideas before committing to build. It's based on Marty Cagan's [Product Opportunity Assessment](https://svpg.com/assessing-product-opportunities/) framework.

**Key principles:**
- **Problem-first thinking** — Understand the problem deeply before jumping to solutions
- **Outcomes over outputs** — Focus on the change you want to see, not activities or deliverables
- **Incremental delivery** — Ship small, learn fast, adjust as you go

This is a living document. Not all sections need to be filled out up front—complete what's known and update as you learn more.

---

# PRD — PROJECT NAME

## 🎯 DACI

See [DACI framework](https://github.com/rianvdm/pm-resources/blob/master/processes/daci.md) for details.

| Role | Person |
|------|--------|
| **Driver** | _Who is responsible for driving this project forward?_ |
| **Approver** | _Who has final decision authority?_ |
| **Contributors** | _Who provides input and does the work?_ |
| **Informed** | _Who needs to be kept in the loop?_ |

---

## 🚀 Product Opportunity Assessment

### What opportunity (problem, need, or desire) will this project address?

_Describe the user/customer problem, need, or desire that motivates this work._

**Good problem statements:**
- Describe a real pain point or unmet need
- Are grounded in evidence (user feedback, data, research)
- Explain the impact of NOT solving this problem
- Avoid solution language

**Example:** "Internal engineers spend 2-3 hours per week searching for documentation across 5+ fragmented systems. This slows onboarding (2+ weeks to productivity) and increases duplicate work as teams can't find existing solutions."

---

### For whom do we address that opportunity?

_Describe the specific target user(s) or customer segment(s)._

**Be specific:**
- Primary users: Who experiences this problem most acutely?
- Secondary users: Who else is affected?
- Include relevant context (team size, frequency of problem, etc.)

**Example:** "**Primary:** Backend engineers deploying new services (200+ engineers across 15+ teams). **Secondary:** SREs who support these services in production."

---

### How will we measure success/make money from this product?

_Define specific, quantifiable metrics that indicate success._

**Good success metrics:**
- Have a baseline and target (e.g., "reduce X from 4 hours to <30 minutes")
- Explain how they'll be measured
- Connect to business value or user outcomes
- Include a timeframe

**Example:** "**Primary metric:** Time to find relevant documentation decreases from 15 minutes to <2 minutes, measured via user survey and instrumented search behavior. Target: 80% of searches result in relevant document found within 2 minutes by end of Q2."

---

### What alternatives are out there?

_Analyze competitive or alternative solutions, including "do nothing."_

**Consider:**
- External products (strengths, weaknesses, cost)
- Internal alternatives or workarounds
- The "do nothing" option and its cost
- Why building is the right choice given these alternatives

---

### What factors are critical to success?

_Define prioritized requirements and non-goals._

**Structure your requirements:**

**Must-have requirements:**
1. [Requirement] — _Why it matters_
2. [Requirement] — _Why it matters_

**Nice-to-have requirements:**
1. [Requirement] — _Why it matters_

**What will be different when shipped:**
- [Concrete change users will experience]
- [Concrete change users will experience]

**Non-goals (explicitly out of scope):**
- [What we are NOT doing and why]
- [What we are NOT doing and why]

---

### How will this product/feature be discovered and adopted?

_Define your go-to-market strategy._

**Include:**
- **Launch plan:** Phases (beta → pilot → GA), timeline, target users for each phase
- **Distribution:** How will users find this? Where does it live?
- **Onboarding:** How will users learn to use it?
- **Adoption targets:** Specific metrics with timeframes (e.g., "200 active users by Week 8")
- **Change management:** How will you drive behavior change?

---

## 😬 Dependencies and Risks

### Known risks

_Identify potential issues that could impact the project._

For each risk, include:
- **Description:** What could go wrong?
- **Likelihood:** Low / Medium / High
- **Impact:** Low / Medium / High
- **Mitigation:** How will you reduce the risk?

**Example:**
> **Risk: Low adoption due to workflow disruption**
> *Likelihood: Medium | Impact: High*
> Engineers may resist changing from familiar (though inefficient) patterns.
> *Mitigation:* Integrate into existing workflows; run pilots with influential teams first; gather and act on feedback quickly.

---

### Cross-team dependencies

_Identify other teams whose work is required for success._

For each dependency:
- **Team/person:** Who do you need?
- **What's needed:** Specific deliverable or support
- **Timeline:** When do you need it?
- **Status:** Have you aligned with them?

---

### Customer Support impact

_Define documentation, training, and support needs._

- **New documentation needed:** [List]
- **Existing documentation updates:** [List]
- **Training:** [Plan]
- **Expected support volume:** [Estimate]

---

### Analytics impact

_Define instrumentation and measurement needs._

- **New events/metrics to track:** [List with properties]
- **Dashboards needed:** [List]
- **Privacy considerations:** [Data retention, access controls]
- **Timeline:** When will instrumentation be ready?

---

### QA impact

_Define how quality will be built in from the start._

- **Automated testing:** [Unit, integration, E2E, performance]
- **Manual testing:** [If needed, what scenarios?]
- **Test data requirements:** [What do you need?]
- **Quality gates for launch:** [What must be true before shipping?]

---

## 😃 Solution Overview

### General overview of how we plan to address the opportunity

_Describe the proposed solution at a high level._

**Include:**
- Solution approach (without over-specifying implementation)
- Key architectural or technology decisions
- User experience overview
- Diagrams or mockups where helpful

_Note: This section describes WHAT we're building, not detailed HOW. Implementation details belong in engineering design docs._

---

### Breakdown of proposed tasks and what goes into each release

_Define incremental releases that deliver value early._

**Each release should:**
- Deliver standalone user value
- Be small and shippable (ideally ≤4 weeks)
- Have clear success criteria
- Include built-in learning and iteration points

**Example structure:**

**Release 1: [Name] (Weeks X-Y)**
- **Goal:** [What user value does this deliver?]
- **Scope:** [What's included?]
- **Success criteria:** [How do we know it worked?]

**Release 2: [Name] (Weeks X-Y)**
- **Goal:** [What user value does this deliver?]
- **Scope:** [What's included?]
- **Success criteria:** [How do we know it worked?]

---

### Estimated time frame

_Provide overall timeline with milestones._

**Include:**
- Major milestones with dates
- Team allocation / resourcing
- Key assumptions
- Risks to timeline and contingency plans
