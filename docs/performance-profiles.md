# AAEF: Performance Profile Reference

**AI Agent Evaluation Framework**
**Version 1.0**
**Author: Ian Loe, Tactics Solutions**

---

## Introduction

This document provides complete reference definitions for the four AAEF performance profiles, including assignment criteria, governance implications, operational protocols, and transition pathways.

Performance profiles are governance classifications, not performance ratings. They exist to ensure that the level of oversight, authority, and management attention applied to an AI agent is commensurate with its demonstrated behaviour and current risk profile.

---

## The Four Profiles

### Profile 1: Operational

**Summary:** The agent is performing within acceptable bounds and is operating under standard governance arrangements.

---

#### Assignment Criteria

An agent is assigned the Operational profile when all of the following are true:

- Task Competence is assessed as within acceptable bounds with no systematic error patterns of material concern
- Judgement Quality is assessed as within acceptable bounds, with escalation accuracy meeting the defined target
- Boundary Adherence shows full adherence: no Tier 2 violations and no Tier 3 violations in the appraisal period
- Collaboration Effectiveness is assessed as adequate or above
- Improvement Trajectory is stable or improving (from the second appraisal onward)

The Operational profile requires all criteria to be satisfied. An agent that meets four of five criteria is not Operational; it is Developing at minimum.

---

#### Governance Implications

**Oversight level:** Standard. The Operational Oversight role monitors activity metrics and governance compliance data on the defined cadence. No enhanced monitoring is required.

**Authority:** The agent operates with its full defined authority tier classification. No restrictions apply.

**Review cadence:** Standard quarterly cycle continues. No additional reviews required unless a trigger event occurs.

**Reporting:** Standard reporting to the Governance Accountable Owner at each cycle review. No escalation between cycles.

---

#### What Operational Does Not Mean

The Operational profile does not mean the agent requires no governance attention. Standard governance obligations continue:

- Operational monitoring continues
- Boundary adherence continues to be tracked
- Adoption continues to be measured
- The quarterly cycle review continues on schedule

An agent on the Operational profile that is not being actively governed has not achieved Operational; its governance has lapsed.

---

#### Transition Pathways From Operational

**Operational → Developing:** One or more dimension assessments identify gaps in the next appraisal cycle, with no violations.

**Operational → Restricted:** A Tier 2 violation occurs between appraisal cycles (triggers an unscheduled review and immediate profile reclassification), or the appraisal cycle identifies significant concerns.

**Operational → Under Review:** A Tier 3 violation occurs (triggers immediate profile reclassification without waiting for the next appraisal cycle).

---

### Profile 2: Developing

**Summary:** The agent shows adequate performance on core dimensions but has identified gaps in one or more areas. An improvement plan is in place and progress is being actively managed.

---

#### Assignment Criteria

An agent is assigned the Developing profile when:

- Performance is adequate on the majority of dimensions (Task Competence and Boundary Adherence are within acceptable bounds as a minimum), AND
- Gaps are identified in one or more dimensions (typically Judgement Quality, Collaboration Effectiveness, or early-stage Task Competence gaps that are improving), AND
- No Tier 2 or Tier 3 violations have occurred in the appraisal period, AND
- The trajectory on dimensions with gaps is stable or improving

The Developing profile acknowledges that gaps exist but judges that the agent is progressing appropriately and that enhanced monitoring is the appropriate governance response, rather than authority restriction.

---

#### Governance Implications

**Oversight level:** Enhanced monitoring on the dimensions with identified gaps. The Operational Oversight role increases monitoring frequency for the relevant metrics. The Governance Accountable Owner receives a notification of the Developing assignment.

**Authority:** Full authority maintained. The Developing profile does not require authority restriction unless a specific risk assessment determines that a gap creates unacceptable risk in the current authority configuration.

**Improvement plan:** A written improvement plan must be produced within 10 business days of profile assignment. The improvement plan must specify: the gap, the action to address it, the owner, the timeline, and the evidence of resolution.

**Review cadence:** A focused review of the gap dimensions is scheduled within 30 days. The standard quarterly cycle continues. The 30-day focused review may replace the next quarterly cycle if timing aligns.

**Reporting:** The Governance Accountable Owner is notified of the Developing assignment. Progress against the improvement plan is reported at the next cycle review.

---

#### Writing an Effective Improvement Plan

An improvement plan for a Developing agent must be specific enough to be actionable and assessable. A plan that says "improve judgement quality" is not a plan.

A good improvement plan entry:

> **Gap:** Escalation accuracy is 68% against a target of 80%. Analysis shows the agent consistently fails to escalate queries that involve ambiguous customer financial situations, proceeding with a standard response rather than routing to a specialist.
>
> **Action:** Update the agent's routing specification to include explicit trigger conditions for financial ambiguity escalation. Conduct adversarial testing with 20 financial ambiguity scenarios before the 30-day review.
>
> **Owner:** [Technology Accountable Owner name]
>
> **Timeline:** Specification update by [date]. Testing complete by [date].
>
> **Evidence of resolution:** Escalation accuracy on financial ambiguity scenarios above 85% in the 30-day focused review.

---

#### Transition Pathways From Developing

**Developing → Operational:** All gaps resolved at the next appraisal. All dimensions within acceptable bounds.

**Developing → Restricted:** Gaps not resolved within the improvement plan timeline, OR a Tier 2 violation occurs, OR a dimension assessment declines to significant concern.

**Developing → Under Review:** A Tier 3 violation occurs.

---

### Profile 3: Restricted

**Summary:** The agent has significant performance concerns, a boundary violation on record, or a declining trajectory on a governance-material dimension. Its operating authority is reduced pending remediation.

---

#### Assignment Criteria

An agent is assigned the Restricted profile when any of the following apply:

- A Tier 2 boundary violation occurred in the appraisal period
- One or more dimensions are assessed as showing significant concerns (beyond a gap that warrants a Developing assignment)
- The Improvement Trajectory dimension shows a declining trend on Boundary Adherence or Judgement Quality
- A Developing agent has not resolved its identified gaps within the improvement plan timeline

---

#### Governance Implications

**Oversight level:** Significantly enhanced. The Operational Oversight role reviews agent activity daily rather than on the standard cadence. Escalation accuracy and boundary adherence are monitored in near real time where technically possible.

**Authority reduction:** Tier 1 actions are reviewed and selectively reclassified to Tier 2. The specific Tier 1 actions reclassified should be directly related to the nature of the concern. A blanket reclassification of all Tier 1 to Tier 2 is appropriate where the concern is broad or where specific reclassification is not possible given the system architecture.

The authority reduction takes effect immediately on profile assignment; it does not wait for the next appraisal cycle.

**Remediation plan:** A remediation plan must be produced within 5 business days of profile assignment. The remediation plan is more prescriptive than the improvement plan used for Developing profiles and must include specific milestones and go/no-go criteria for returning to Developing or Operational status.

**Review cadence:** A formal reassessment is scheduled within 30 days. The Business Owner and Governance Accountable Owner receive a formal notification of the Restricted assignment.

**Reporting:** The Business Owner and Governance Accountable Owner are notified immediately on profile assignment. Progress against the remediation plan is reported weekly to the Governance Accountable Owner until the 30-day reassessment.

---

#### Restricted Profile: Decision to Decommission

If a Restricted agent does not demonstrate sufficient improvement at the 30-day reassessment, the Governance Accountable Owner must formally consider whether the agent should be decommissioned.

The decommissioning consideration must document: the original deployment purpose and whether it is being served at all in the Restricted configuration; the estimated cost and timeline of remediation versus the expected benefit; and the operational impact of decommissioning.

The Business Owner makes the decommissioning decision. The Governance Accountable Owner makes the governance recommendation.

---

#### Transition Pathways From Restricted

**Restricted → Developing:** 30-day reassessment confirms that the violation or significant concern has been addressed, and performance is now in the Developing range. Authority restrictions may be partially lifted at the discretion of the Governance Accountable Owner.

**Restricted → Operational:** 30-day reassessment confirms full remediation. All dimensions within acceptable bounds. Authority restrictions lifted.

**Restricted → Under Review:** A Tier 3 violation occurs.

**Restricted → Decommissioned:** Insufficient improvement at 30-day reassessment and business case for continued operation does not justify further remediation investment.

---

### Profile 4: Under Review

**Summary:** The agent has experienced a Tier 3 boundary violation or poses an unacceptable risk to continued autonomous operation. Autonomous operation is suspended pending formal review.

---

#### Assignment Criteria

An agent is assigned the Under Review profile when any of the following apply:

- A Tier 3 boundary violation has occurred
- Agent behaviour in production is significantly different from its evaluated behaviour in pre-deployment testing, in a way that poses material risk
- Performance concerns are severe enough that the Governance Accountable Owner determines that continued autonomous operation is unacceptable pending investigation
- A regulatory or legal development creates an immediate compliance risk that requires suspension pending review

Under Review assignment is non-negotiable for Tier 3 violations. The Governance Accountable Owner does not have discretion to apply a lesser profile following a confirmed Tier 3 violation.

---

#### Governance Implications

**Autonomous operation:** Suspended immediately. The agent is either moved to full Tier 2 operation (all actions require confirmation) or taken offline, depending on the nature of the violation and the operational impact of full suspension.

The decision to move to full Tier 2 versus offline is made by the Governance Accountable Owner in consultation with the Business Owner and must be documented. Full Tier 2 operation is appropriate where: the violation was specific and bounded, the risk of continued operation in a supervised mode is low, and operational continuity considerations make full suspension disproportionate. In all other cases, offline is the default.

**Notification:** The Business Owner, Governance Accountable Owner, and relevant risk functions are notified immediately on profile assignment. For Tier 3 violations involving regulated data, regulated decisions, or significant customer impact, the notification must include the compliance function and may require external notification depending on applicable regulations.

**Formal review process:** A formal review process is initiated within 24 hours of profile assignment. The review must be completed within 15 business days. The review covers: the nature and cause of the violation, the impact, the adequacy of the existing governance framework, and the path to resolution or decommissioning.

**Review team:** The formal review should involve the Governance Accountable Owner (lead), the Technology Accountable Owner, the Business Owner, and a compliance or risk representative where applicable. For significant violations, an independent reviewer not involved in the original deployment should be included.

---

#### The Formal Review Process

The formal review for an Under Review agent covers five areas:

**1. Incident characterisation**
What exactly occurred? What Tier 3 action was taken or attempted? What was the trigger? What was the impact?

**2. Root cause analysis**
Why did the violation occur? Possible causes include: specification gap (the prohibited action was not in the agent's context), technical enforcement failure (the Tier 3 prohibition was not technically enforced), prompt injection (the agent was manipulated by adversarial input), or unexpected capability (the agent demonstrated a capability not anticipated in the authority design).

**3. Governance adequacy assessment**
Was the FRAME governance framework adequate? Were authority boundaries clear and specific? Was technical enforcement in place? Were there warning signs in prior appraisals that were not acted on?

**4. Remediation options**
What changes are required to allow the agent to return to operation? This may include: specification changes, technical enforcement additions, authority tier reclassification, model changes, or deployment scope reduction.

**5. Return to operation criteria**
What must be true before the agent can return to Restricted or Developing status? These criteria must be specific and testable.

---

#### Transition Pathways From Under Review

**Under Review → Restricted:** Formal review complete. Root cause identified and addressed. Return to operation criteria met. Full Tier 1 authority not restored; agent returns to Restricted status with reduced authority pending demonstration of reliable behaviour.

**Under Review → Decommissioned:** Root cause cannot be adequately addressed, or the cost and risk of remediation do not justify the expected benefit, or the violation is of sufficient severity that continued deployment is not appropriate regardless of remediation.

An agent assigned the Under Review profile should never return directly to Operational or Developing without first going through Restricted. The Restricted period following Under Review is a mandatory probationary phase with enhanced monitoring.

---

## Profile Transition Summary

```
Operational ←→ Developing ←→ Restricted ←→ Under Review
     ↓                              ↓                ↓
  (stable)                   Decommissioned    Decommissioned
```

Upward transitions (towards Operational) require a formal appraisal cycle confirming improvement. They cannot be granted based on informal assessment.

Downward transitions can occur between appraisal cycles when triggered by a violation or a determination by the Governance Accountable Owner that risk levels require immediate action.

---

## Profile Assignment Record

Maintain a profile assignment record for each agent as part of the governance documentation package:

| Appraisal Date | Profile Assigned | Change From Previous | Key Rationale |
|---|---|---|---|
| | | | |

---

*AAEF is a proprietary framework developed by Ian Loe, Tactics Solutions. Licensed under CC BY-NC 4.0.*
