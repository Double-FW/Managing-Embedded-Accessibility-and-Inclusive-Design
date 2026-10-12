---
title: "LLM Agent Reference for Embedded Accessibility & Inclusive Design"
version: "1.0"
author:
  name: "Double-FW, Gareth Ford Williams"
date: "2026-10-11"
license: "CC-BY-4.0"
language: "en"
repository: "github.com/Double-FW/Managing-Embedded-Accessibility-and-Inclusive-Design"
artifact_type: "guidance/agent-knowledge"
use_case:
  - "agent-decisioning"
  - "evidence-archival"
  - "policy-enforcement"
schema_version: "agent-metadata-v1"
entities:
  roles:
    - "Sponsor"
    - "Product Owner"
    - "Engineering Lead"
    - "Design Lead"
    - "QA Lead"
  system_outputs:
    - "Acceptance Conditions"
    - "Automated Test Results"
    - "Manual Verification Results"
  agent_tasks:
    - "generate_code"
    - "generate_test_cases"
    - "raise_tickets"
  evidence_types:
    - "evidence_refs"
    - "artifacts"
    - "research_findings"
  retention_policies:
    - "acceptance_conditions"
    - "ai_permissions_log"
    - "barriers_remediation"
notes: |
  - This front-matter provides machine-readable metadata for discovery and validation.
  - Update `schema_version` when front-matter structure changes.
---

# LLM Agent Reference for Embedded Accessibility & Inclusive Design

**Version**: 1.0  
**Basis**: Managing Embedded Accessibility and Inclusive Design (11 October 2026)  
**Purpose**: Enable LLM agents to identify roles, responsibilities, system tasks, and interdependencies in product delivery pipelines with accessibility and inclusive design requirements.

## 0. MACHINE-READABLE METADATA & POLICY SCHEMA

This file is now structured to support machine-readability for automation and validation. The YAML front matter above declares the canonical metadata that can be consumed by tooling without parsing narrative markdown. In addition, agents and CI systems can validate policy entries against a minimal policy schema.

```yaml
schema_version: "policy-schema-v1"
required_fields:
  - id
  - title
  - description
  - severity
  - owner
  - decision_gate
  - created_at
fields:
  id:
    type: string
    pattern: "^P-[0-9]{3,}$"
  title:
    type: string
  description:
    type: string
  severity:
    type: string
    enum: ["info", "low", "medium", "high", "critical"]
  owner:
    type: object
    properties:
      name: { type: string }
      role: { type: string }
      contact: { type: string }
  decision_gate:
    type: string
  applicability:
    type: array
    items: { type: string }
  conditions:
    type: array
    items: { type: string }
  actions:
    type: array
    items: { type: string }
  retention_days:
    type: integer
  decision_allowed:
    type: boolean
  created_at:
    type: string
    format: date-time
  updated_at:
    type: string
    format: date-time
  approved_by:
    type: array
    items: { type: string }
```

Example policy entry:

```yaml
id: "P-001"
title: "Escalation: Evidence Completeness Requirement"
description: "An escalation event must include traceable evidence and reproducible steps before Product Owner review."
severity: "high"
owner:
  name: "Product Management"
  role: "Product Owner"
  contact: "mailto:product-owner@example.com"
decision_gate: "Product Owner"
applicability:
  - "escalation.request"
  - "barrier.notification"
conditions:
  - "event.evidence_refs.length >= 1"
  - "evidence_completeness.traceable == true"
  - "evidence_completeness.reproducible == true"
actions:
  - "if all conditions true and decision_allowed == true: agent may prepare evidence summary and auto-route to decision_gate"
  - "if conditions unmet: agent must create barrier ticket with 'insufficient_evidence' tag and route to Product Owner"
retention_days: 3650
decision_allowed: false
created_at: "2026-10-12T00:00:00Z"
updated_at: "2026-10-12T00:00:00Z"
approved_by:
  - "Sponsor"
```

This metadata and schema should be treated as the minimal machine-readable contract for automation, evidence retention, and escalation governance. Agents should validate policy files before trusting or enforcing rules.

---

## 1. ROLES & RESPONSIBILITIES MATRIX

### 1.1 Human Roles (RACI Accountable Owners)

| Role | Primary Responsibility | Key Evidence Owned | Escalation Authority |
|------|------------------------|-------------------|----------------------|
| **Sponsor** | Executive funding, commitment, conflict resolution | Organizational commitment, escalation decisions | N/A (Top) |
| **Product Owner** | Service outcome, release decision, funding | Barrier visibility, outcome gaps, release readiness | Sponsor |
| **Product Manager** | Backlog quality, prioritization, scope changes | Acceptance conditions, proposed changes log | Product Owner |
| **Engineering Lead** | Engineering capability, AI controls, technical readiness | Generated work reviews, recurring failure analysis | Product Owner |
| **Architect** | Platform, integration, semantics, state, recovery | Technical decisions, high-risk assumption proofs | Engineering Lead |
| **Design Lead** | Interaction, journey, focus, navigation, patterns | Design decisions, shared pattern library | Product Manager |
| **Content Lead** | Accessible language, labels, alternatives, structures | Content review evidence, generated content assessment | Product Manager |
| **Engineers** | Implement accessible behavior, data contracts, components | Code review, barrier reproduction, regression tests | Engineering Lead |
| **QA Lead** | Verification coverage, evidence quality, no-single-owner accountability | Coverage register, manual results, test coordination | Engineering Lead |
| **Platform Lead** | Reproducible environments, pipeline controls, monitoring | Configuration versioning, evidence preservation | Engineering Lead |
| **Research Lead** | Inclusive recruitment, methods, lived-experience interpretation | Research methods, survey results, segment analysis | Data Lead / Product Owner |
| **Data Lead** | Instrumentation, experiment analysis, reporting | Denominators, uncertainty measures, segment differences | Research Lead |
| **Operations Lead** | Accessible support, operational workflows, barrier capture | Barrier logs, recovery evidence, resolution confirmation | Product Owner |
| **Programme Coordinator** | Cross-team coordination, shared guidance, capability | Champions charter, network capability, maturity evidence | Sponsor |

### 1.2 Support Functions & Advisers

- **Supplier Lead**: Supplier evidence, escalation
- **Legal/Privacy/Security Advisers**: Requirements within remits, regulatory assessment
- **Champions Network**: Cross-functional peers with protected time, clear remit, and operational influence

---

## 2. SYSTEM TASKS & INTERDEPENDENCIES

### 2.1 Core System Outputs (Data & Artifacts)

Systems produce outputs that flow into downstream decision-making and evidence. Each output has sources and dependent downstream tasks.

| System Output | Producing Role(s) | Key Dependencies (Inputs) | Downstream Consumers | Archive/Retention Purpose |
|---------------|-------------------|--------------------------|----------------------|---------------------------|
| **User Needs & Affected Users** | Research Lead, Product Manager | Discovery phase interviews, disabled user participation | All delivery roles; Design, QA, Operations | Business case justification, evidence for decision-making and service scope |
| **Acceptance Conditions** | Product Manager, QA | User needs, design decisions, applicable requirements (WCAG, EAA, best-practice) | Engineers, QA, Design; Release gate | Verification criteria, audit trail, acceptance evidence |
| **Design Decisions & Patterns** | Design Lead, Design practitioners | User needs, research findings, accepted standards | Engineers, Content, QA, AI instructions | Pattern library evolution, precedent setting, accessibility decisions |
| **Content Review Results** | Content Lead | Generated content (from AI or authors), design context, labels | Engineers, QA, Product; Release gate | Evidence of conformance, content accessibility matching |
| **Baseline Requirements & Policy** | Sponsor, Engineering Lead, QA Lead | Legal/regulatory analysis, organizational constraints | All teams, AI governance | Accountability, scope protection, deviation tracking |
| **AI Permissions & Controlled Instructions** | Engineering Lead, Platform Lead | Approved knowledge registry, bounded authority rules, data boundaries | AI systems, QA, Platform | Governance audit, model and prompt control evidence |
| **Code Review & AI Output Assessment** | Engineers, Engineering Lead | AI-generated code or components, acceptance conditions | QA, Product Manager, Release gate | Technical quality evidence, regression protection |
| **Automated Test Results & Coverage Register** | QA Lead, Platform Lead | Test code, configured rules (axe-core 4.13), CI/CD pipeline | QA lead, Release gate, manual testing scope | Conformance proof, coverage evidence |
| **Manual Verification Results** | QA practitioners, Test practitioners, Engineers | Acceptance conditions, keyboard & assistive technology checks | QA Lead, Release gate, Design | Task completion evidence, barrier reproduction track |
| **Barriers & Remediation Tickets** | QA, Operations, Research | Manual results, support logs, survey feedback, user reports | Product Manager, Design, Engineering, Research | Prioritization data, policy learning, resolution tracking |
| **Technical Remediation Evidence** | Test practitioners, Engineers | Barrier tickets, code changes, regression tests | QA Lead, Researchers, Product Manager | Verification of fix, outcome improvement evidence |
| **Research Findings & ASK Survey Data** | Research Lead, Data Lead, Analysts | Inclusive recruitment, survey design, segment analysis | Design, Engineering, Product, Operations | Customer/employee insight archive |
| **Outcome Measures & Segment Analysis** | Data Lead, Analysts, Researchers | ASK data (navigation, task completion, time, confidence, effort, assistance), support data | Product Owner, Design, Engineering, Operations | Experience trend evidence |
| **Release Decision & Evidence Summary** | Product Owner | Engineering Lead & QA Lead input, all evidence streams | All delivery team, Operations | Decision log, go/no-go rationale, support readiness |
| **Operational Barriers & Support Logs** | Operations Lead, Support practitioners | Live user interactions, support tickets, access requests | Research, QA, Engineering, Product | Feedback loop, recurrence prevention |
| **Supplier Capability Assessment** | Supplier Lead, Architect, QA | Supplier evidence, procurement conditions, AI system evaluation | Procurement, Architect, Product Owner | External dependency audit |
| **Experiment Design & Study Identifiers** | Research Lead, Data Lead | Approved questions, accessibility checks, triggers, distinct URLs/identifiers | AI systems, QA, Operations | Study reproducibility and evidence integrity |
| **AI Governance Inventory & Controls** | Engineering Lead, Platform Lead, Programme Coordinator | AI systems in use, inclusion objectives, evidence requirements, escalation rules | All business owners, engineering, product | AI control trail and governance evidence |
| **Maturity Evidence & Improvement Roadmap** | Programme Coordinator, Dimension owners | Evidence from all six dimensions, disabled participant input | Sponsor, Champions, Business owners | Organizational learning and improvement tracking |

### 2.2 Interdependency Flows (How Outputs Enable Other Tasks)

**Legend**: → = "feeds into"; ◇ = "required before"; ● = "optional input to improve"

#### Discovery & Investment Phase
```
User Needs & Affected Users
├─→ Acceptance Conditions (define what accessibility means for this service)
├─→ Design Decisions (inform inclusive interaction patterns)
├─→ Research Methods (scope inclusive recruitment for this journey)
└─→ Baseline Requirements (identify affected populations for priority)
```

#### Design & Architecture Phase
```
Baseline Requirements + Acceptance Conditions
├─→ Design Decisions (map interaction, focus, recovery for each condition)
├─→ AI Instructions (bind AI-generated design to design patterns)
└─→ Supplier Capability Assessment (evaluate external services against conditions)

Design Decisions
├─→ Content Decisions (labels, instructions follow design patterns)
├─→ Code Review Criteria (engineers implement specified patterns)
└─→ Manual Test Plan (QA checks each condition against design)
```

#### Development & AI Generation
```
AI Permissions & Controlled Instructions
├─→ Code Review & AI Output Assessment (engineers verify output matches policy)
├─→ Automated Test Results (confirm generated code passes configured checks)
└─→ Barriers & Remediation (flag policy deviations for investigation)

Code Review & AI Output Assessment
├─→ Automated Test Results (run tests on reviewed code)
├─→ Manual Verification (QA confirms code behavior matches specification)
└─→ Barriers & Remediation (feed unresolved issues to ticket queue)
```

#### Verification & Release
```
Automated Test Results + Manual Verification Results + Content Review Results
├→ Release Decision (aggregate evidence streams before go/no-go)
├→ Barriers & Remediation (unresolved failures cascade to Product Manager)
└→ Operational Readiness (Operations & Support prepare for release)

Barriers & Remediation Tickets
├→ Product Manager (prioritize by impact & obligation)
├→ Design Lead (propose interaction/pattern improvements)
└→ Engineering Lead (assign remediation or scope change)
```

#### Operations & Continuous Improvement
```
Release Decision + Operational Barriers & Support Logs
├→ Research Findings & ASK Survey (establish post-release baseline)
├→ Outcome Measures & Segment Analysis (compare pre/post experience)
└→ Operational Barriers Feed (route unresolved barriers back to Product Manager)

Research Findings ● (improves) Barriers & Remediation (prioritization using lived experience)
Outcome Measures ● (improves) Design Decisions (evidence-based pattern updates)
Operational Barriers ● (improves) AI Instructions (add edge cases to system knowledge)
Support Logs ● (improves) Manual Test Plan (expand coverage for recurring issues)
```

#### Governance & AI Evolution
```
Barriers & Remediation + Research Findings + Outcome Measures
├→ AI Governance Inventory & Controls (model and permission updates)
├→ Baseline Requirements & Policy (policy evolution)
└→ Maturity Evidence & Improvement Roadmap (dimension-level tracking)

AI Governance Inventory & Controls
├→ AI Permissions & Controlled Instructions (new approvals)
└→ Code Review Criteria (updated assessment rules)

Maturity Evidence & Improvement Roadmap ● (informs) Supplier Capability Assessment
(shared standards for future procurements)
```

---

## 3. SYSTEM TASK MATRIX: Agents & Interdependencies

### 3.1 AI System Roles (Where LLM Agents Operate)

| AI Task | Input Sources | Responsible Role | Key Dependencies | Output | Quality Gate |
|---------|---------------|------------------|------------------|--------|--------------|
| **Generate Code/Components** | AI Instructions, Design Decisions, Acceptance Conditions | Engineers (review & validate) | Must have: approved patterns, WCAG compliance scope | Code artifact | Engineering review with regression evidence |
| **Generate Test Cases** | Acceptance Conditions, Design Decisions, Manual Test Plan | QA Lead (approve coverage) | Acceptance conditions must be specific; prior manual results inform edge cases | Test cases | QA sign-off for coverage completeness |
| **Generate Content (Labels, Instructions, Alternatives)** | Acceptance Conditions, Design Decisions, Content Lead guidance | Content Lead (review in actual context) | Design decisions specify interaction and linguistic context | Content output | Human review before publishing |
| **Raise & Prioritize Tickets** | Barriers & Remediation data, Research Findings, Support Logs | Product Manager (approve priority) | Barriers must have: reproducible evidence, affected users, applicable requirement | Ticket and prioritization | Product Owner and triage check |
| **Design Experiments** | Research Methods, Approved Questions, Outcome Measures baseline | Research Lead (approve design) | Prior baseline must exist; study period & allocation rules defined | Experiment design | Research and ethics approval |
| **Aggregate & Report Results** | ASK Survey data, Support data, Segment analysis filters | Data Lead (validate analysis) | Data completeness, denominators, uncertainty measures specified | Report with caveats | Data validation and stakeholder review |
| **Update Design Patterns** | Technical Remediation Evidence, Outcome Measures, Design Decisions | Design Lead (approve & retain) | Evidence must show improvement survived releases; prior pattern must be known | Updated pattern library | Design review and evidence validation |
| **Monitor Compliance & Flag Deviations** | Automated test results, manual results, requirement baseline | QA Lead (assess severity & route) | Baseline requirements, test configuration pinned | Deviation record or alert | QA severity classification |
| **Suggest Process Improvements** | Maturity Evidence, Barriers history, Champions network feedback | Programme Coordinator (contextualize for workflow) | Six dimensions & current level must be defined | Improvement roadmap | Programme validation |
| **Document AI Model Changes** | Model versions, prompt changes, tool/dependency updates | Engineering Lead (approve & record) | Change history template, pre-auth model list | Change record with decisions | Engineering approval |

### 3.2 Human Tasks That Modify AI Instructions or Require AI Review

| Task | RACI Responsible | RACI Accountable | AI Role (If Any) | Evidence Requirement |
|------|-----------------|------------------|------------------|----------------------|
| Baseline Requirements & Policy setting | Engineering Lead, QA | Sponsor | AI drafts candidates for review | Legal/regulatory scope, organizational constraints, signed |
| AI Permissions & Controls review | Platform Lead, Engineering Lead | Engineering Lead | AI may draft policy options | Approved knowledge registry, separated from AI output checking |
| Code Review of AI output | Engineers | Engineering Lead | N/A (human only) | Criteria comparison, regression test results, AI model version |
| Design Pattern Approval | Design practitioners | Design Lead | AI may suggest pattern updates from outcome data | Evidence of improvement, release survival, disabled user input |
| Content Review | Content practitioners | Content Lead | N/A unless AI-generated; then human review against context | Actual interface context, user research alignment |
| Manual Test Plan | QA practitioners | QA Lead | AI may generate test cases, QA approves | Coverage register, edge cases from barriers history |
| Research Method Approval | Research practitioners | Research Lead | AI may suggest questions; must be pre-approved | Accessible recruitment, ethical review, disabled participation |

---

## 4. REPORTING & EVIDENCE ARCHIVING MATRIX

### 4.1 What to Archive & Why

**Archive Purpose Categories**:
- **Accountability**: Prove who decided what, when, and with what evidence.
- **Audit Trail**: Reconstruct decisions, especially deviations and escalations.
- **Learning Loop**: Turn barriers and outcomes into pattern updates and policy evolution.
- **Regression Prevention**: Verify fixes survive, catch recurrence, expand test coverage.
- **Compliance**: Meet WCAG, EAA, and contractual obligations with evidence.
- **Organizational Memory**: Preserve context for future teams and stakeholder onboarding.

| Evidence Type | Retention Focus | Archive Format | Minimum Retention | Queries/Reports Needed |
|---------------|-----------------|-----------------|-------------------|------------------------|
| **Acceptance Conditions** | What accessibility means for each service; linked requirement | Versioned checklist, commit history | Full lifecycle + 2 years post-support | "Coverage by dimension", "Change history" |
| **AI Permissions & Controls Log** | Which AI tasks authorized, rules active, model versions tied to decisions | Timestamped changelog with decision rationale | Full lifecycle + 2 years | "What was authorized and when" |
| **Code Review Records** | Which AI outputs were reviewed, by whom, criteria applied, issues found | Commit message, pull request comments, evidence links | Full lifecycle (VCS) | "Code review coverage" |
| **Test Configuration & Baseline** | Which rules active (axe-core 4.13 pinned version, WCAG A/AA tags), manual scope | Versioned configuration file, rule inventory | Each release + 2 years | "Test configuration drift" |
| **Manual Test Results** | Keyboard, assistive technology checks; what barriers found; reproducibility | Test case ID, barrier ID, screenshot/video, reproduction steps | Per release + 2 years | "Barrier reproduction and pass/fail history" |
| **Barriers & Remediation Tickets** | What failed, affected users, evidence source, remediation plan, outcome check | Ticket with tags (impact, obligation, evidence link, status) | Full lifecycle | "Open and resolved barrier trends" |
| **Technical Remediation Evidence** | How barrier was fixed, code changes, regression tests added, outcome verified | Commit, PR, test additions, outcome measure (if applicable) | Full lifecycle + 1 year | "Fix verification and regression proof" |
| **Research Methods & Recruitment** | Who participated (disability diversity), accessibility of survey method, ethical review | Recruitment plan, participant demographics, survey tool accessibility records | Full lifecycle + 2 years | "Participation coverage and method quality" |
| **Survey & Experiment Data (ASK)** | Distinct study IDs, survey period, release version, segment filters, raw data with uncertainty | CSV export pinned before study closure, study metadata, segment report | Full lifecycle + 2 years | "Segment-level comparisons and uncertainty" |
| **Outcome Measures & Segment Analysis** | Task completion %, task time, confidence, effort, assistance need; denominators & missing data | Report with response counts, confidence intervals, group-level summaries | Full lifecycle + 2 years | "Outcome trends by segment" |
| **Release Decisions** | What shipped, evidence summary, concerns recorded, go/no-go rationale | Signed release form linking acceptance evidence, waiver (if any) | Full lifecycle + 5 years | "Release evidence and sign-off history" |
| **Operational Barriers & Support Logs** | Support tickets with accessibility flags, recovery evidence, whether issue resolved | Support ticket, barrier classification, resolution status | Full lifecycle + 2 years | "Support-driven barriers and recovery path" |
| **Supplier Capability Assessment** | Evaluation criteria met/gaps, committed obligations, ongoing monitoring | Assessment report, supplier evidence, commitment timeline | Contract lifecycle + 2 years | "Supplier obligations and risk status" |
| **Design Pattern Library** | Pattern definition, acceptance conditions, accessibility notes, when added/updated, rationale | Pattern version, linked evidence (e.g., outcome measure proving improvement) | Full lifecycle + 2 years | "Pattern history and evidence trail" |
| **AI Governance Inventory** | AI systems in use, inclusion objectives, permissions, evidence requirements, model versions | System catalog with metadata, approval chain, model pinning, links to instances | Full lifecycle + 2 years | "AI system inventory and policy trace" |
| **Escalation & Deviation Log** | Scope changes, waivers, conflicts escalated; affected users, interim access, resolution date | Escalation form with decision, responsible owner, dated resolution | Full lifecycle + 5 years | "Escalation timelines and resolved exceptions" |
| **Champions Network Records** | Member roles, remit, protected time, training, outcomes (issues raised, improvements implemented) | Network directory, meeting notes, action log, outcome evidence | Full lifecycle + 2 years | "Champion capacity and action tracking" |
| **Maturity Assessment & Roadmap** | Six dimensions, current level, evidence gaps, planned actions, funding, responsible owners | Assessment record, dimension breakdowns, roadmap with due dates, progress | Full lifecycle + 5 years | "Maturity trend and improvement roadmap" |

### 4.2 Evidence Streams to Report (Management Dashboards)

**Three Streams for Release Readiness** (from guide):
1. **Conformance against requirements** (Acceptance Conditions ✓, Automated tests ✓, Manual verification ✓)
2. **Automated & manual verification results** (Coverage register, barriers log)
3. **Inclusive user outcomes** (ASK survey, support dependency, segment analysis)

**Governance Measures** (Non-compliance detectors):
- Requirement coverage by service (% of in-scope conditions with evidence)
- Unresolved failures by severity (count by impact & obligation)
- Scope changes & waivers (tracked, dated, justified, resolved?)
- Champion capacity (% with protected time, active escalations resolved)
- Escalation resolution rate (time from escalation to decision)
- Requirements surviving scope changes (% of inclusion requirements removed?)

**AI-Specific Measures**:
- AI permission audit (% of tasks bounded, % of generated code reviewed)
- Model version & change tracking (pinned version, changes approved & monitored)
- Regression detection (failures in areas where fix was implemented before)
- Test coverage from AI (% of generated code with automated + manual tests)

**Outcome Measures** (Customer/Employee Experience):
- Comparable experience by segment (task completion, time, confidence, effort, assistance)
- Support dependency (% of segment requiring escalation)
- Barrier recurrence (re-opened tickets in same category)
- Net experience score (satisfaction, accessibility confidence, inclusive design perception)

### 4.3 Recommended Archive Structure

```
/evidence
  /acceptance-conditions/{service-id}/
    v1.0-YYYY-MM-DD.md  (versioned, linked to commit/PR)
    
  /ai-governance/
    ai-permissions-{YYYY-MM-DD}.md  (timestamped log)
    model-versions.json  (active models & pinned versions)
    
  /code-review/
    {PR-ID}/
      review-checklist.md
      criteria-applied.md
      ai-model-version.txt
      
  /test-config/
    axe-core-rules-v4.13.json  (pinned config)
    wcag-tags.json  (active standards)
    manual-scope.md  (what's not automated)
    
  /barriers-remediation/
    barriers-{YYYY-Q}.csv  (quarterly export)
    ticket-ID/{ticket}/
      barrier-report.md
      evidence.{jpg,mp4,txt}
      remediation-pr.md
      outcome-check.md
      
  /research-outcomes/
    studies/
      study-{ID}/
        design.md  (approved questions, recruitment, study period)
        data-export-FINAL.csv  (snapshot before closure)
        segment-analysis.md  (denominators, confidence)
        limitations.md  (response rate, dropout, missing data)
    ask-survey-data/
      {release-version}-{YYYY-MM-DD}.csv
      
  /release-decisions/
    {version}/
      release-form-SIGNED.md
      evidence-summary.md
      waivers-{if-any}.md
      support-readiness.md
      
  /design-patterns/
    library.md
    pattern-{name}/
      definition.md
      accessibility-notes.md
      changelog.md
      linked-evidence.md  (outcome measures)
      
  /maturity-assessment/
    annual-{YYYY}.md  (all six dimensions)
    roadmap-{YYYY}.md  (actions, owners, deadlines)
    historical/
      {YYYY}/  (past assessments for trend tracking)
```

---

## 5. OPERATING RHYTHM & AGENT DECISION RULES

### 5.1 When Agents Should vs. Shouldn't Act

**Agent May Autonomously**:
- Suggest design patterns from outcome data (Design Lead approval required before release)
- Draft test cases from acceptance conditions (QA Lead approves coverage)
- Generate code from approved instructions (Engineers review before merge)
- Flag deviations (QA Lead routes & prioritizes)
- Aggregate & report survey data with caveats (Data Lead validates analysis)
- Suggest improvement roadmap items (Programme Coordinator contextualizes for approval)

**Agent Must Route for Human Decision**:
- Policy changes (Sponsor escalation route)
- AI permission/model changes (Engineering Lead signature required)
- Scope deviations affecting accessibility (Product Owner + escalation if needed)
- Release go/no-go (Product Owner decision)
- New research methods (Research Lead approval for ethics & accessibility)
- Supplier capability decisions (Procurement + Architect + QA review)
- Waiver/exception requests (Sponsor decision log)

### 5.2 Evidence Completeness Checks (Agents Should Validate)

Before routing to decision-makers:
- **Is the evidence traceable?** (Can you link back to source: barrier ticket, research finding, test result?)
- **Is it reproducible?** (Are steps, configuration, context versioned and archived?)
- **Is uncertainty documented?** (Response rate? Confidence interval? Missing data?)
- **Are affected users named?** (Who benefits or is harmed by this decision?)
- **Are requirements identified?** (WCAG criterion? EAA obligation? Best-practice label?)
- **Is the responsible owner clear?** (Who will act on this? Can they be contacted?)

---

## 6. LLM AGENT PROMPT FRAMEWORK

When an LLM agent receives a product delivery task, it should:

1. **Identify the Role(s) Involved**
   - "This task involves [Product Manager], [QA Lead], [Design Lead]. Who is Accountable for the decision?"

2. **Map Input Sources**
   - "What evidence does this task depend on? (Check: User Needs? Acceptance Conditions? Prior Research? AI Instructions?)"

3. **Identify Downstream Consumers**
   - "Whose work depends on the output of this task? (Check: QA, Release gate, AI instructions, Pattern library?)"

4. **Check Archive Requirements**
   - "What evidence must be retained? (Check: decision rationale, configuration versions, segment data, reproducibility details?)"

5. **Validate Before Escalation**
   - "Is the evidence complete? (Check: traceable, reproducible, uncertainty documented, affected users named, requirement identified, owner clear?)"

6. **Route or Execute**
   - If human decision required: escalate with evidence summary + validation checklist.
   - If autonomous permitted: execute, log decision + versions, route evidence to archive + downstream consumers.

---

## 7. EXAMPLE: Agent Decision Flow for Barrier Resolution

```
Barrier Ticket Received: "Search form inaccessible to keyboard users"
├─ Identify Inputs:
│  ├─ Barrier: keyboard navigation broken (QA & Operations reported)
│  ├─ Design Decisions: search pattern requires focus management
│  └─ Acceptance Conditions: WCAG 2.2 Level AA (keyboard accessible)
│
├─ Generate Remediation Plan:
│  ├─ Review Design Lead's search pattern library
│  ├─ Generate code fix from AI Instructions (bounded authority: code only, not tests)
│  └─ Generate test cases from Acceptance Conditions
│
├─ Responsible = Engineers; Accountable = Engineering Lead
│
├─ Queue for Review:
│  └─ Engineers + Engineering Lead + QA review AI output
│     (Code Review & AI Output Assessment)
│
├─ Outputs to Archive:
│  ├─ Barrier ticket ID
│  ├─ Technical fix (PR with reproduction steps, tests added)
│  ├─ Outcome check (did manual test pass? Did segment experience improve?)
│  └─ Pattern update candidate (if fix proves durable)
│
├─ Route to Downstream:
│  ├─ QA Lead: add test to regression suite + coverage register
│  ├─ Design Lead: consider pattern update (if outcome data supports improvement)
│  ├─ Data Lead: flag segment for post-release outcome re-measurement
│  └─ Programme Coordinator: log "keyboard" barrier for trend analysis
│
└─ Success Criteria:
   ├─ Code merged with tests
   ├─ Manual verification passed
   ├─ Outcome measure shows improvement (if post-release study running)
   └─ Barrier not re-opened in same sprint/release
```

---

## 8. REFERENCES & SOURCES

- **Primary Framework**: AI Accessibility Maturity Model (Double FW Ltd.)
- **Standards**: WCAG 2.2 Level A & AA; EAA Annex I Functional Performance Criteria
- **Automation Baseline**: axe-core 4.13 (pinned version, rules configured per organizational policy)
- **Research & Outcomes**: Accessiblethinking.com ASK AI survey (six dimensions: navigation, task completion, task time, confidence, effort, assistance)
- **Governance**: Embedded operating model with distributed RACI roles, no dedicated accessibility audit, champions network for operational influence
- **Evidence Streams**: Conformance (requirements + tests), Verification results (automated + manual), Inclusive outcomes (user/employee research)

---

## 9. MAINTENANCE & UPDATES

**Owner**: Programme Coordinator  
**Review Cadence**: Quarterly (after material org changes, model updates, or policy evolution)  
**Version History**:
- v1.0 (11 Oct 2026): Initial embedded model framework aligned with Managing Embedded Accessibility guide

**To Update This File**:
1. Identify the change (new role, new AI task, new evidence type, policy evolution)
2. Update the relevant section (matrix, interdependency, archive, rules)
3. Route to Programme Coordinator for organizational validation
4. Link to decision log & commit message
5. Notify Champions network of changes
