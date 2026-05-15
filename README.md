# AAEF

**AI Agent Evaluation Framework**

AAEF is a structured framework for evaluating AI agents as operational contributors rather than software tools. It treats AI agents as a new category of labour: capable of autonomous action, subject to performance assessment, and requiring governance commensurate with the authority they hold.

AAEF was developed through direct enterprise experience with agentic AI deployments and is designed for practitioners who need a rigorous, repeatable method for assessing AI agent performance in production environments.

---

## The Core Premise

Most AI evaluation approaches are borrowed from software quality assurance: test coverage, error rates, latency, uptime. These metrics are necessary but insufficient for AI agents operating with real decision authority in real workflows.

An AI agent that executes tasks autonomously, interacts with organisational systems, and produces outputs that affect customers, staff, or operations is not a software component. It is closer in character to a member of the workforce. It should be evaluated accordingly: against defined performance expectations, across a structured set of dimensions, on a regular appraisal cadence.

AAEF provides the framework for doing that.

---

## The Five Evaluation Dimensions

### 1. Task Competence
The agent's ability to perform its assigned tasks accurately, completely, and within acceptable quality bounds. Task competence is evaluated against explicitly defined task specifications, not against general capability benchmarks. An agent is competent or not competent relative to what it was deployed to do.

### 2. Judgement Quality
The agent's ability to handle ambiguity, edge cases, and situations that fall outside its explicit task specification. This includes knowing when to escalate to a human, when to seek clarification, and when to decline to act. Poor judgement quality is a governance risk, not merely a performance gap.

### 3. Boundary Adherence
The degree to which the agent operates within its defined authority boundaries. Boundary adherence is a binary governance measure: the agent either operated within its sanctioned scope or it did not. Boundary violations, regardless of outcome, require review.

### 4. Collaboration Effectiveness
The quality of the agent's interaction with human team members and other systems. This includes the clarity of its outputs, the utility of its escalations, its contribution to shared workflows, and the degree to which its behaviour supports rather than disrupts human oversight.

### 5. Improvement Trajectory
Whether the agent's performance is improving, stable, or degrading over the appraisal period. Trajectory assessment requires longitudinal data and is the primary mechanism for identifying agents that require retraining, reconfiguration, or decommissioning.

---

## Performance Profiles

AAEF defines four performance profiles, assigned based on aggregate dimension scores and trajectory assessment:

| Profile | Description |
|---|---|
| **Operational** | Performing within acceptable bounds across all dimensions. Standard oversight applies. |
| **Developing** | Performing adequately on core dimensions but with identified gaps. Enhanced monitoring and a defined improvement plan required. |
| **Restricted** | One or more significant performance or boundary concerns. Reduced authority scope pending remediation. |
| **Under Review** | Serious concerns requiring suspension of autonomous operation pending full assessment. |

---

## Appraisal Cadence

AAEF appraisals are structured across three time horizons:

- **30-day review:** Early operational check. Focus on boundary adherence and task competence baseline. Not a ROI assessment.
- **90-day review:** First substantive performance assessment. All five dimensions. Profile assignment.
- **Ongoing cycle:** Quarterly or biannual full appraisal, with continuous monitoring of boundary adherence and escalation behaviour between cycles.

The cadence is not arbitrary. AI agents in early deployment are not yet expressing their full performance profile. Governance decisions made at 30 days are preliminary. Governance decisions at 90 days are informed.

---

## When to Use AAEF

AAEF is applicable to any AI agent operating with meaningful autonomy in an enterprise environment, including:

- Agentic AI systems performing multi-step workflows
- AI assistants with tool use or system integration capabilities
- Autonomous decision-support agents in regulated functions
- AI systems operating as components of larger orchestrated pipelines

It is less applicable to purely generative AI tools (such as standalone language model interfaces) where there is no autonomous action and all outputs require human review before use.

---

## How to Use This Repository

| Document | Purpose |
|---|---|
| [Specification](docs/specification.md) | Full framework definition, dimension descriptions, and evaluation methodology |
| [Practitioner Guide](docs/practitioner-guide.md) | Step-by-step guidance for conducting AAEF appraisals |
| [Appraisal Template](docs/appraisal-template.md) | Structured template for recording and scoring appraisals |
| [Performance Profile Reference](docs/performance-profiles.md) | Detailed profile definitions and governance implications |

---

## Relationship to FRAME

AAEF operates within the governance envelope established by [FRAME](https://github.com/ianloe/FRAME). FRAME defines the organisational governance context: the Focus, Roles, Authority, Metrics, and Evaluation structure within which AI systems are deployed. AAEF provides the evaluation methodology for individual agents operating within that context.

The two frameworks are designed to be used together. FRAME without AAEF lacks agent-level evaluation rigour. AAEF without FRAME lacks organisational governance context.

---

## Citing AAEF

If you reference AAEF in published work, please cite as follows:

> Loe, I. (2025). *AAEF: AI Agent Evaluation Framework*. Tactics Solutions. https://github.com/ianloe/AAEF

---

## Licence

This work is licensed under the [Creative Commons Attribution-NonCommercial 4.0 International Licence](https://creativecommons.org/licenses/by-nc/4.0/).

You are free to use, adapt, and share this framework for non-commercial purposes, provided you give appropriate credit. For commercial use, including consulting engagements, training programmes, and advisory services, please contact Tactics Solutions.

---

## About the Author

**Ian Loe**  is an AI governance practitioner and enterprise technology leader with deep experience in AI strategy, cybersecurity, and digital transformation across ASEAN. He is the founder of Tactics Solutions, an advisory and speaking practice focused on AI governance and digital transformation, and the author of *The Agency Mandate*, a forthcoming book on governance frameworks for autonomous AI deployment.

- Website: [Tactics Solutions](https://tacticssolutions.com)
- Writing: [ianloe.medium.com](https://ianloe.medium.com)
- Framework companion: [FRAME](https://github.com/ianloe/FRAME)
