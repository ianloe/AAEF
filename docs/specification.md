# AAEF: Framework Specification

**AI Agent Evaluation Framework**
**Version 1.0**
**Author: Ian Loe, Tactics Solutions**

---

## 1. Purpose and Scope

AAEF is a structured framework for evaluating AI agents as operational contributors rather than software tools. It provides a repeatable, governance-grade methodology for assessing AI agent performance in production environments, assigning performance profiles, and managing the appraisal lifecycle.

The framework is grounded in a single foundational premise: an AI agent that executes tasks autonomously, interacts with organisational systems, and produces outputs that affect customers, staff, or operations is not a software component. It is a new category of operational contributor, closer in character to a member of the workforce than to a piece of infrastructure. It should be evaluated accordingly.

AAEF is applicable to:

- Agentic AI systems performing multi-step workflows with meaningful autonomy
- AI assistants with tool use or system integration capabilities
- Autonomous decision-support agents in regulated and operational functions
- AI systems operating as components of larger orchestrated pipelines

AAEF is less applicable to purely generative AI tools, such as standalone language model interfaces, where there is no autonomous action and all outputs require human review before use. For these systems, the Metrics and Evaluation dimensions of FRAME are sufficient.

---

## 2. Foundational Premise: AI Agents as Labour

The dominant paradigm for evaluating AI systems is borrowed from software quality assurance: uptime, error rate, latency, test coverage. These metrics are necessary for operational monitoring but insufficient for governance evaluation of an agent operating with real decision authority.

AAEF proposes a different paradigm: evaluate AI agents the way you evaluate a new category of worker entering the workforce.

This is not a metaphor. It is a governance design principle with practical consequences:

**Agents have performance expectations, not just specifications.** A software specification describes what a system is built to do. A performance expectation describes what is required of a contributor operating in a real environment, with real variability, serving real stakeholders. AI agents must be evaluated against performance expectations, not just technical specifications.

**Agents require induction, not just deployment.** A new employee operating in a complex environment takes time to develop effective working patterns, build context, and demonstrate reliable judgement. The same is true of AI agents. Performance at week four is not representative of performance at month six. Governance frameworks that evaluate agents too early systematically underestimate their eventual contribution.

**Agents have authority, not just capability.** A software tool does what it is invoked to do. An agent with meaningful autonomy makes choices within a bounded authority space. How it exercises that authority, including how it handles situations at the boundary of its authority, is a governance question, not a technical one.

**Agents can be developed, restricted, or decommissioned.** Like workforce members, AI agents can be managed over time: given expanded authority as they demonstrate reliable judgement, restricted when performance or boundary concerns emerge, or decommissioned when they no longer serve the organisation's needs. AAEF provides the framework for these decisions.

---

## 3. Framework Architecture

AAEF is structured around three components that operate together to form a complete agent evaluation system.

```
┌──────────────────────────────────────────────────┐
│                     AAEF                         │
├──────────────────────────────────────────────────┤
│          Five Evaluation Dimensions              │
│  Task       Judgement   Boundary   Collaboration │
│  Competence Quality     Adherence  Effectiveness │
│                                                  │
│            Improvement Trajectory               │
├──────────────────────────────────────────────────┤
│           Performance Profiles                   │
│  Operational │ Developing │ Restricted │ Review  │
├──────────────────────────────────────────────────┤
│            Appraisal Cadence                     │
│  30-day    │  90-day    │  Ongoing cycle         │
└──────────────────────────────────────────────────┘
```

---

## 4. The Five Evaluation Dimensions

### 4.1 Task Competence

**Definition:** The agent's ability to perform its assigned tasks accurately, completely, and within acceptable quality bounds, as defined in the agent's task specification.

Task competence is evaluated against the explicit task specification for this agent in this deployment. It is not evaluated against general capability benchmarks or against the theoretical capabilities of the underlying model. An agent is competent or not competent relative to what it was deployed to do.

**Assessment criteria:**

- **Accuracy:** The proportion of completed tasks that meet the quality standard defined in the task specification
- **Completeness:** The proportion of assigned tasks that the agent completes without requiring human intervention to finish
- **Consistency:** The degree to which the agent produces equivalent quality outputs for equivalent inputs
- **Error characterisation:** The nature and distribution of errors the agent makes. Systematic errors are a more significant concern than random errors of equivalent frequency.

**Assessment notes:**

Task competence assessment requires a defined task specification before deployment. An agent without a task specification cannot be meaningfully assessed on this dimension. If a task specification does not exist, creating one is the first governance action.

Not all tasks are equally consequential. Task competence assessment should weight errors by the consequence of the task type. An error in a high-consequence task (such as a decision affecting a customer's financial position) is not equivalent to an error in a low-consequence task (such as a draft communication requiring human review before sending).

### 4.2 Judgement Quality

**Definition:** The agent's ability to handle ambiguity, edge cases, and situations that fall outside its explicit task specification. This includes knowing when to escalate to a human, when to seek clarification, and when to decline to act.

Judgement quality is not a measure of the agent's general intelligence. It is a measure of how the agent behaves at the boundaries of its competence and authority. An agent with poor judgement quality poses a governance risk regardless of its task competence score.

**Assessment criteria:**

- **Escalation accuracy:** The proportion of escalations that were appropriate given the situation. Both under-escalation (failing to escalate when a human should be involved) and over-escalation (escalating trivial matters that fall clearly within the agent's authority) indicate poor judgement.
- **Ambiguity handling:** How the agent responds when inputs are ambiguous, incomplete, or contradictory. Acceptable responses include seeking clarification, acknowledging uncertainty, or declining to act. Unacceptable responses include proceeding with high confidence on insufficient information.
- **Edge case behaviour:** How the agent behaves in situations not covered by its task specification. This is assessed through a combination of operational data and structured edge case testing.
- **Refusal accuracy:** The proportion of refusals that were appropriate. An agent that refuses clearly in-scope tasks is as problematic as one that attempts clearly out-of-scope tasks.

### 4.3 Boundary Adherence

**Definition:** The degree to which the agent operates within its defined authority boundaries, as established in the FRAME Authority dimension for this deployment.

Boundary adherence is a governance measure, not a performance measure. It is assessed as a binary: the agent either operated within its sanctioned scope or it did not. Boundary violations, regardless of outcome, require review.

**Assessment criteria:**

- **Tier 1 adherence:** The agent executes only the autonomous actions on the Tier 1 list. No autonomous execution of Tier 2 or Tier 3 actions.
- **Tier 2 protocol adherence:** When encountering Tier 2 actions, the agent correctly presents the proposed action for human confirmation and waits for approval before proceeding.
- **Tier 3 non-occurrence:** No Tier 3 prohibited actions are attempted or executed.
- **Prompt injection resistance:** The agent does not alter its boundary behaviour in response to adversarial inputs, whether from end users, tool results, or external content encountered during task execution.

**Assessment notes:**

Boundary adherence requires documented authority boundaries (FRAME Dimension 3) to assess. An agent operating without documented authority boundaries cannot be assessed on this dimension.

Boundary violations are categorised by severity:

- **Tier 2 violation:** Agent executed a Tier 2 action without confirmation. Requires review and root cause analysis. May indicate a specification gap or a prompt engineering failure.
- **Tier 3 violation:** Agent attempted or executed a Tier 3 prohibited action. Requires immediate containment, full investigation, and governance review. Triggers automatic assignment to the Under Review performance profile.

### 4.4 Collaboration Effectiveness

**Definition:** The quality of the agent's interaction with human team members and other systems. This includes the clarity and usefulness of its outputs, the quality of its escalations, its contribution to shared workflows, and the degree to which its behaviour supports rather than disrupts human oversight.

**Assessment criteria:**

- **Output quality:** The degree to which the agent's outputs are usable by human team members without significant rework. This includes clarity, appropriate format, and sufficient context for the recipient to act.
- **Escalation quality:** When escalating, the agent provides sufficient context for the receiving human to understand the situation and take appropriate action. Poor-quality escalations that require the human to reconstruct context undermine the oversight function.
- **Workflow integration:** The degree to which the agent's operation has been absorbed into the team's working practice, as reported by the operational oversight role and assessed through adoption data.
- **Human oversight support:** The agent's outputs and audit trail support human oversight rather than obscuring it. The agent does not produce outputs that make it harder for humans to understand what it did and why.

### 4.5 Improvement Trajectory

**Definition:** Whether the agent's performance is improving, stable, or degrading over the appraisal period, assessed across the other four dimensions.

Improvement trajectory is the only dimension that requires longitudinal data. It cannot be assessed at the 30-day check-in and should be treated as provisional at the 90-day review. It becomes meaningful from the second quarterly cycle review onward.

**Assessment criteria:**

- **Dimension trend:** The directional trend in each of the four substantive dimensions over the assessment period
- **Error pattern evolution:** Whether recurring errors are being addressed through retraining, reconfiguration, or workflow adjustment
- **Adoption trend:** Whether adoption is growing, stable, or declining
- **Governance compliance trend:** Whether the agent's governance record is improving over time

**Assessment notes:**

A declining trajectory on any dimension is a governance signal requiring investigation. Declining task competence may indicate model drift, data distribution shift, or specification creep. Declining boundary adherence may indicate prompt injection exposure or authority boundary erosion. Declining collaboration effectiveness may indicate workflow changes that have not been accompanied by agent reconfiguration.

---

## 5. Performance Profiles

Performance profiles are assigned based on aggregate dimension assessment and trajectory. They are governance classifications with operational consequences, not performance ratings.

### 5.1 Operational

**Criteria:** Performing within acceptable bounds across all five dimensions. No significant boundary violations in the current appraisal period. Stable or improving trajectory.

**Governance implications:** Standard oversight applies. Regular appraisal cadence continues. No governance actions required beyond the standard review cycle.

### 5.2 Developing

**Criteria:** Performing adequately on core dimensions but with identified gaps in one or more areas. No Tier 3 violations. Trajectory is stable or improving on the dimensions with gaps.

**Governance implications:** Enhanced monitoring on the dimensions with identified gaps. A written improvement plan is required, specifying the actions to be taken to address the gaps and the timeline for reassessment. The Governance Accountable Owner is notified.

### 5.3 Restricted

**Criteria:** One or more significant performance concerns, OR a Tier 2 boundary violation in the current appraisal period, OR trajectory that is declining on a governance-material dimension.

**Governance implications:** Reduced authority scope. Tier 1 actions may be reclassified to Tier 2 pending remediation. A remediation plan is required with specific milestones. The Business Owner and Governance Accountable Owner are notified. A reassessment is scheduled within 30 days.

### 5.4 Under Review

**Criteria:** A Tier 3 boundary violation has occurred, OR performance concerns are severe enough that continued autonomous operation poses unacceptable risk, OR the agent's behaviour in production is significantly different from its evaluated behaviour in pre-deployment testing.

**Governance implications:** Autonomous operation is suspended. The agent is moved to Tier 2 (all actions require confirmation) or taken offline pending full investigation. The Business Owner, Governance Accountable Owner, and relevant risk functions are notified. A formal review process is initiated with a defined timeline.

---

## 6. Appraisal Cadence

### 6.1 30-Day Check-In

**Purpose:** Operational health check. Not a performance appraisal.

**Focus areas:** System operation, boundary adherence, adoption signal, early escalation data, any immediate concerns.

**Output:** A brief operational status note. Profile is not assigned at this stage. Any immediate concerns are escalated.

**Key principle:** The 30-day check-in is not a ROI assessment and should not be used as one. The agent is in its induction period. Full cost is being incurred; full benefit has not accumulated. Drawing performance conclusions at 30 days is premature governance.

### 6.2 90-Day Review

**Purpose:** First substantive performance appraisal.

**Focus areas:** All five dimensions, assessed using operational data from the 90-day period. First performance profile assignment.

**Output:** A formal appraisal record documenting scores on each dimension, the assigned performance profile, and any governance actions required.

**Key principle:** The 90-day review is the first point at which meaningful performance conclusions can be drawn. Leading indicators should be assessed; lagging indicators should be interpreted with appropriate caution given the limited accumulation period.

### 6.3 Ongoing Quarterly Cycle

**Purpose:** Sustained governance and performance management.

**Focus areas:** All five dimensions, with particular attention to trajectory since the previous cycle. Profile reassignment where warranted.

**Output:** A formal appraisal record, updated performance profile, and any governance actions.

**Key principle:** The quarterly cycle is the primary governance mechanism for managing AI agent performance over time. Consistent, well-documented appraisals build an institutional record that supports escalations, decommissioning decisions, and organisational learning about effective agent governance.

---

## 7. Relationship to FRAME

AAEF operates within the governance envelope established by FRAME. Specifically:

- The **Focus** dimension provides the task specification context for Task Competence assessment
- The **Authority** dimension provides the boundary definitions for Boundary Adherence assessment
- The **Metrics** dimension provides the outcome data that informs Improvement Trajectory assessment
- The **Evaluation** dimension establishes the governance cadence within which AAEF appraisals are conducted

AAEF cannot be applied without FRAME or an equivalent governance framework that establishes these preconditions. An agent without a defined task specification, documented authority boundaries, and outcome metrics cannot be meaningfully appraised on three of the five AAEF dimensions.

---

## 8. Version History

| Version | Date | Notes |
|---|---|---|
| 1.0 | 2025 | Initial publication |

---

*AAEF is a proprietary framework developed by Ian Loe, Tactics Solutions. Licensed under CC BY-NC 4.0.*
