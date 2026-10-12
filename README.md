# Managing Embedded Accessibility and Inclusive Design

A practical guide for organisations that want to embed accessibility and inclusive design into ordinary product delivery, governance, research, operations, and AI-assisted workflows.

This repository brings together:

- a human-readable operating model for accessibility and inclusive design
- an agent-oriented reference for LLMs and AI assistants operating in product delivery contexts
- role, evidence, governance, and release guidance that reflects real organisational responsibilities

## Repository purpose

The purpose of this repository is to help teams answer a basic but critical question:

> Who owns the requirement, who demonstrates that it works, and whose experience could still be missing from the evidence?

The content is designed for both:

- humans working in product, design, engineering, research, quality, operations, and leadership
- AI agents and automated assistants that participate in planning, coding, testing, summarising evidence, and raising issues

## What is in this repository

- `Managing_Embedded_Accessibility_and_Inclusive_Design.md` — the main human-readable framework and guidance document
- `agent.md` — a dedicated agent reference that explains roles, responsibilities, decision boundaries, evidence requirements, and workflow rules for LLM agents
- `LICENSE` — repository licensing information

## Recommended reading order

### For people

1. Start with `Managing_Embedded_Accessibility_and_Inclusive_Design.md`
2. Review the RACI and governance sections
3. Use the evidence and operating rhythm guidance in planning and release decisions

### For AI agents

1. Read `agent.md` first
2. Treat it as a decision framework and operating contract
3. Use the human decision routing rules before changing policy, release status, or governance structures

## Core themes

The repository is built around a simple model:

- accessibility and inclusive design are embedded into normal delivery responsibilities, not treated as a separate, isolated audit function
- evidence is produced throughout the lifecycle, not only at the end
- product owners, engineering leads, QA, design, content, research, and operations all have accountable responsibilities
- AI systems must be governed with bounded permissions, human review, and traceable evidence
- release decisions should depend on conformance, verification evidence, and inclusive outcome measures

## Human-readable framework

The main document describes:

- an embedded operating model for accessibility and inclusive design
- roles and responsibilities across the organisation
- product delivery RACI mappings
- governance and evidence retention expectations
- research, measurement, and outcome tracking
- AI governance controls for workflows involving automation and generated outputs
- maturity progression and operational rhythm

The key principles include:

- accessibility should be funded and owned by product outcomes, not added as an afterthought
- no-scoping and no-silent-decision rules are essential for inclusion commitments
- evidence must exist before a release can be considered ready
- inclusive user outcomes should be treated as a first-class measure alongside technical conformance and verification

## Agentic framework

The `agent.md` file adds an explicitly agent-oriented lens. It defines:

- the roles and responsibilities that humans hold within the model
- the tasks where AI agents may assist autonomously
- the decisions that require human validation or escalation
- evidence completeness checks before an agent routes a concern upward
- a prompt framework that helps agents reason using the right organisational context

### Agent decision boundaries

The agent guidance distinguishes between:

- tasks agents may autonomously help with, such as drafting tests or identifying barriers from evidence
- tasks that must be routed for human decision, including policy changes, release go/no-go, waivers, supplier decisions, and research method approvals

### Agent evidence expectations

Agents are expected to confirm that their outputs are:

- traceable to source evidence
- reproducible with clear context
- accompanied by uncertainty or limitations where relevant
- explicit about affected users and requirements
- routed to the correct owner for action

## Decision model summary

### Human responsibilities

Typical accountable roles include:

- Sponsor — organisational commitment and escalation
- Product Owner — service outcome and release decision
- Product Manager — backlog quality and prioritisation
- Engineering Lead — technical readiness and AI controls
- Architect — platform and design integrity
- Design Lead — interaction and journey quality
- Content Lead — accessible language and labels
- QA Lead — verification coverage and evidence quality
- Platform Lead — reproducible environment and pipeline controls
- Research Lead — inclusive recruitment and meaningful evidence
- Data Lead — measurement, analysis, and uncertainty
- Operations Lead — support workflows and barrier recording
- Programme Coordinator — maturity evidence and cross-team alignment

### AI/agent responsibilities

LLM agents can support tasks such as:

- generating draft content, tests, or code under approved instructions
- summarising evidence and identifying patterns
- flagging barriers and gaps in verification
- suggesting improvement opportunities based on outcome data

However, agents should not be treated as final decision-makers for:

- policy changes
- scope deviations affecting inclusion
- release readiness decisions
- AI permission changes
- supplier commitments
- waivers and escalations

## Evidence and archive expectations

The framework emphasises that evidence is retained for accountability, learning, auditability, and release confidence. It recommends preserving:

- acceptance conditions
- AI governance records
- code review evidence
- automated and manual test configuration
- barrier and remediation records
- research data and outcome analysis
- release decisions and operational barriers
- design pattern updates and maturity assessments

## Use cases

This repository is useful for:

- product teams embedding accessibility into normal delivery
- engineering teams applying AI-assisted development under safe governance
- QA and release functions seeking evidence-driven sign-off
- research and data teams measuring inclusive outcomes
- leaders managing organisational maturity and accountability
- AI practitioners building safe, auditable agent workflows

## Suggested operating rhythm

The guide suggests working at multiple cadences:

- every change: check requirements, AI permissions, and test coverage
- every sprint or delivery cycle: review blockers, evidence gaps, and outcome signals
- monthly: review repeat issues, missed workflows, and shared learning
- quarterly and after material changes: review maturity, governance, and funding decisions

## Repository structure

```text
.
├── LICENSE
├── README.md
├── Managing_Embedded_Accessibility_and_Inclusive_Design.md
├── agent.md
└── .github/ (if added later for workflows or automation)
```

## How to use this repository in practice

### For a product or service team

- define service-specific acceptance conditions
- allocate named owners to each role in the RACI
- maintain evidence through the delivery lifecycle
- review barriers and release readiness using evidence, not assumptions

### For an AI-enabled engineering team

- pin model versions and policy controls
- keep AI permissions bounded and explicit
- require human review of generated outputs
- document evidence and route escalations appropriately

### For governance or leadership

- assess maturity across the six organisational dimensions
- review recurring barriers and research results
- ensure inclusion requirements survive scope change discussions
- maintain a continuous improvement roadmap

## Contribution and maintenance

This repository is intended as a living framework. Updates should be tied to:

- organisational or policy changes
- new evidence sources or research methods
- revised AI governance controls
- new lifecycle requirements or operational realities

Recommended update pattern:

1. identify the change
2. update the relevant section in the main guide or agent reference
3. validate the implications for roles, evidence, and release gates
4. retain the decision record and communicate updates to relevant stakeholders

## License

This repository is licensed under the terms in the `LICENSE` file.

## Summary

This project combines a practical human-facing accessibility framework with an explicit AI-agent operating model. It is designed to help organisations do more than talk about inclusion: it provides a way to assign ownership, maintain evidence, govern automation, and improve outcomes over time.

For the full detailed guidance, read:

- `Managing_Embedded_Accessibility_and_Inclusive_Design.md`
- `agent.md`

For an agent operating in this domain, `agent.md` is the actionable reference and should be treated as the decision and governance companion to the human-readable guide.

---

This repository is maintained as a documentation and governance resource for accessibility and inclusive design in embedded, AI-assisted delivery environments.
















































































































































































































































































































































































































































































































