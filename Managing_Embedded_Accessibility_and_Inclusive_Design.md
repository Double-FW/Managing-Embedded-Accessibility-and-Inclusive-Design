Managing embedded accessibility and inclusive design

A practical guide for product teams and organisational leaders

11 October 2026 • Version 1.0

# An embedded operating model

Accessibility and inclusive design can be managed through ordinary product and business responsibilities. Product owners fund the outcomes, practitioners deliver them, and leaders require evidence that people can participate. A dedicated accessibility team is not a prerequisite for this allocation of work, but the necessary capability, time and authority must still exist.

This guide describes what a fully embedded model could look like in an organisation using AI to generate code, raise tickets, gather feedback and support design optimisation. It establishes delivery ownership first, then explains how an accessibility manager and champions network can strengthen the model across the organisation.

The aim is comparable experience: people should be able to achieve worthwhile outcomes with appropriate autonomy, confidence, dignity and effort. Technical conformance is one part of the evidence. Customer and employee experience must also influence what the organisation designs, funds and changes. \[1\]

**"Who owns the requirement, who demonstrates that it works, and whose experience could still be missing from our evidence?"**

## The delivery baseline

Adopt WCAG 2.2 Level A and AA for applicable web content, use an explicitly configured axe-core 4.13 baseline, and document additional inclusive design practices. Identify relevant legal and contractual duties separately. AAA criteria may be adopted as best practice without being relabelled as AA obligations. \[2–3\]

Maintain three distinct evidence streams: conformance against requirements; automated and manual verification results; and inclusive user outcomes. A clean automated run or a high satisfaction score cannot substitute for the other streams. Record unassessed areas and incomplete checks explicitly.

## A model that does not depend on a final audit

Teams build evidence throughout delivery, including human assessment where automation is insufficient. Removing a periodic audit does not remove verification. Peer challenge and independent review remain available for uncertain or consequential decisions. The maturity model explicitly includes AI evaluation and independent review capability, so a permanent ban on such review would undermine its full delivery. \[1\]

## Roles and the work they own

Allocate these functions to named people. A small team may combine roles, but managers should check capacity and competence before doing so. The role labels below are used consistently in the RACI tables.

| **Role**         | **Primary responsibility and evidence**                                                                                                                                    |
| ---------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Sponsor          | An executive with authority over funding and escalation. Owns the organisational commitment, protects inclusion objectives and resolves conflicts between business areas.  |
| Product owner    | Owns the service outcome and release decision. Funds accessibility work and research; maintains visibility of unresolved barriers and outcome gaps.                        |
| Product manager  | Owns backlog quality and prioritisation. Connects user needs, acceptance conditions, evidence and remediation; records proposed scope changes.                             |
| Engineering lead | Owns engineering capability, technical readiness and AI delivery controls. Requires review of generated work and addresses recurring causes of failure.                    |
| Architect        | Owns platform and integration capabilities, semantics, content models, authentication, state and recovery. Records decisions and proves high-risk assumptions.             |
| Design lead      | Owns interaction and journey design, including focus, navigation, errors and adaptation. Maintains shared patterns and uses evidence to improve them.                      |
| Content lead     | Owns accessible language, labels, instructions, alternatives and content structures. Reviews generated content in its actual context.                                      |
| Engineers        | Implement accessible behaviour, data contracts and components. Review AI output, reproduce barriers, repair causes and add regression protection.                          |
| QA lead          | Owns verification coverage and evidence quality. Coordinates automated, manual, keyboard and assistive technology checks without becoming the sole owner of accessibility. |
| Platform lead    | Owns reproducible environments, pipeline controls, versioned configuration, monitoring and rollback. Preserves evidence across releases.                                   |
| Research lead    | Owns inclusive recruitment, survey methods and lived-experience interpretation. Ensures people unable to complete a journey can still contribute.                          |
| Data lead        | Owns instrumentation and experiment analysis. Reports denominators, uncertainty, segment differences and limits on causal conclusions.                                     |
| Operations lead  | Owns accessible support and operational workflows. Captures barriers, supports recovery and confirms whether reported problems are resolved.                               |

Supporting functions: the supplier lead owns supplier evidence and escalation; legal, privacy and security advisers establish requirements within their remits. Each business workflow also has a named business owner who remains accountable for its inclusive operation.

## Protect inclusion throughout the lifecycle

Include accessibility and inclusive outcomes in the business case, funded scope, acceptance conditions and definition of done. A champion can challenge a decision, but only leadership-backed controls can prevent a deadline or cost pressure from silently removing the requirement.

| **Point in the workflow**     | **Required management action**                                                                                                          | **Evidence to retain**                                                               |
| ----------------------------- | --------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| Discovery and investment      | Identify affected users, essential tasks, dependencies and intended inclusive outcomes. Allocate delivery and research capacity.        | User needs, business owner, funded requirements and baseline measures.               |
| Procurement and architecture  | Evaluate external services, employee tooling and AI systems before commitment. Prove uncertain capabilities.                            | Supplier findings, integration constraints and architecture decisions.               |
| Design and content            | Specify alternative interactions, understandable content and recovery. Include disabled participants in relevant research.              | Design decisions, content requirements, research findings and acceptance conditions. |
| Development and AI generation | Use maintained component patterns and approved instructions. Review generated code and content against the same criteria as other work. | Change history, model and instruction versions, reviews and test results.            |
| Verification and release      | Check whole tasks and relevant states. Resolve failed criteria and record uncertainty. Require an explicit release decision.            | Coverage register, manual results, known issues and release record.                  |
| Operation and optimisation    | Combine technical signals with support, research and segmented outcome data. Re-evaluate changes after release.                         | Survey periods, experiment results, incident trends and improvement decisions.       |
| Replacement and retirement    | Preserve accessible routes during migration, including communications, data export and support.                                         | Migration assessment and evidence that essential tasks remain available.             |

### Make the no descoping commitment enforceable

Inclusion requirements should not be removable through routine backlog reprioritisation. If delivery pressure threatens them, the product owner changes the implementation, funding, delivery scope or release date while retaining the required outcome. The same rule applies to suppliers and AI-generated changes.

A proposed deviation must identify affected users, evidence, interim access, the responsible owner and a dated resolution. It follows the sponsor's escalation route and applicable obligations. It remains an unresolved gap; internal approval cannot convert a failure into conformance. Serious barriers trigger a hold or rollback under the agreed release policy.

The QA lead may withhold a readiness recommendation, and champions can invoke the escalation route. The product owner retains release accountability and cannot silently override a mandatory control. Record the authority, response deadline and cover arrangements before work starts.

## RACI for product delivery

Use the conventional RACI model throughout: Responsible performs the work; Accountable owns the decision and outcome; Consulted contributes before the decision; Informed receives the result. Assign one Accountable owner to each activity and at least one Responsible role. The same person may hold both where appropriate.

These are proposed allocations, not responsibilities prescribed by WCAG. Replace role labels with named owners before adoption. "QA" means the QA lead and test practitioners; "Design" means the design lead and practitioners. "Advisers" means the relevant legal, privacy or security function.

| **Activity**                              | **R <br>Responsible**           | **A <br>Accountable** | **C <br>Consulted**                      | **I <br>Informed**              |
| ----------------------------------------- | ------------------------------- | --------------------- | ---------------------------------------- | ------------------------------- |
| Set organisational baseline and funding   | Product owner; engineering lead | Sponsor               | QA; advisers; research lead              | All teams                       |
| Define service outcomes and funded scope  | Product manager                 | Product owner         | Design; research lead; QA                | Engineering lead                |
| Write acceptance conditions               | Product manager; QA             | Product manager       | Design; content lead; engineers          | Product owner                   |
| Approve architecture and integrations     | Architect; engineers            | Architect             | QA; design; security; platform lead      | Product manager                 |
| Specify interaction and journey behaviour | Design practitioners            | Design lead           | Research lead; QA; engineers             | Product manager                 |
| Specify content and alternatives          | Content practitioners           | Content lead          | Design; research lead; QA                | Product manager                 |
| Implement and review code                 | Engineers                       | Engineering lead      | Architect; QA; design                    | Product manager                 |
| Configure automated tests and pipeline    | QA; platform practitioners      | Platform lead         | Engineering lead; architect              | Product manager                 |
| Maintain manual coverage and evidence     | Test practitioners; engineers   | QA lead               | Design; content lead; research lead      | Engineering lead; product owner |
| Validate and prioritise tickets           | QA; research lead; engineers    | Product manager       | Operations lead; data lead               | Product owner                   |
| Decide release readiness                  | Engineering lead; QA lead       | Product owner         | Research lead; operations lead; advisers | Delivery team                   |

### Human accountability in an AI workflow

AI tools may perform assigned steps, but are not RACI role holders. Every automated action belongs to the Responsible human role and an Accountable owner. Pre-authorised automation can run without a new approval each time when its permissions, limits and escalation conditions are explicit.

## RACI for evidence and organisational governance

This allocation works without a dedicated accessibility team. The "programme coordinator" is a named duty assigned by the sponsor to an existing manager with funded time. It maintains cross-team coordination; it does not take over each team's delivery responsibilities.

| **Activity**                                       | **R <br>Responsible**                   | **A <br>Accountable** | **C <br>Consulted**                              | **I <br>Informed** |
| -------------------------------------------------- | --------------------------------------- | --------------------- | ------------------------------------------------ | ------------------ |
| Approve research methods and survey triggers       | Research practitioners                  | Research lead         | Data lead; privacy; design                       | Product manager    |
| Analyse outcomes and experiment results            | Analysts; researchers                   | Data lead             | QA; design; engineering lead                     | Product owner      |
| Authorise a design experiment                      | Data lead; research lead; engineers     | Product owner         | QA; design; privacy                              | Operations lead    |
| Verify technical remediation                       | Test practitioners; engineers           | QA lead               | Design; architect                                | Product manager    |
| Evaluate remediation outcomes                      | Researchers; analysts                   | Research lead         | QA; design; affected participants                | Product owner      |
| Capture and route operational barriers             | Support practitioners; QA               | Operations lead       | Research lead; engineering lead                  | Product manager    |
| Assess supplier capability and commitments         | Supplier practitioners                  | Supplier lead         | Architect; QA; advisers                          | Product owner      |
| Maintain AI delivery permissions and controls      | Platform practitioners; engineers       | Engineering lead      | QA; privacy; security; programme coordinator     | Product owner      |
| Protect inclusion in a business workflow           | Workflow practitioners; champions       | Business owner        | Programme coordinator; affected people; advisers | Sponsor            |
| Fund and protect the champions network             | Programme coordinator; line managers    | Sponsor               | Business owners; champions                       | All teams          |
| Maintain network capability and shared guidance    | Champions; nominated practitioners      | Programme coordinator | Research lead; QA; engineering lead              | Business owners    |
| Maintain maturity evidence and improvement roadmap | Programme coordinator; dimension owners | Sponsor               | Champions; disabled participants; advisers       | All teams          |

## The value of an accessibility team and champions network

An accessibility manager or team can make distributed ownership more reliable by maintaining the organisational conditions in which teams succeed. Its remit should include capability, shared evidence, AI governance, escalation and the maturity roadmap. It should have access to the sponsor and the authority to challenge decisions across business boundaries.

In the RACI, the accessibility manager takes the programme coordinator function and is Consulted on baselines, AI controls, scope changes, supplier risks and significant experiments. It is Responsible for specialist guidance and maturity review. Product and business owners retain delivery accountability.

### Establish a network with operational influence

Recruit champions across product, engineering, design, research, content, procurement, HR, communications and operations. Give each a clear remit, protected working time, training, a deputy and a reporting route. Include disabled employees and customers in the work through accessible, appropriately supported participation. Champions do not substitute for their lived experience.

Champions bring inclusion into planning and scope discussions, identify weak hand-offs, check whether required evidence exists and share proven improvements. They help teams use the controls and escalate when those controls fail. They are not unpaid replacement specialists and should not acquire accountability for every defect in their area.

### Protect scope and maintain capability

The accessibility manager maintains the common policy, decision templates, learning resources and network charter. Line managers remain responsible for releasing champions' time. The sponsor protects the budget and escalation authority. Together, they make inclusion a continuing condition of delivery rather than a discretionary project activity.

A network should track whether inclusion requirements survived scope changes, whether unresolved concerns reached decision-makers and whether repeated issues led to changes in shared systems. Counting champions or training attendance alone does not demonstrate effective coverage.

### Provide specialist challenge and AI governance

The team reviews high-risk assumptions, supports complex interaction and assistive technology questions, and maintains approved accessibility knowledge used by AI. It works with engineering, research, privacy and security to define automation boundaries and to evaluate the effects of model, prompt, tool and workflow changes.

Its cross-organisational view is particularly valuable when local optimisation shifts effort elsewhere. For example, reducing call handling time may make support harder for people who need longer to communicate. The team can connect operational metrics with customer evidence and challenge an improvement that creates exclusion in another part of the journey.

### Close the improvement loop

The team helps turn findings into updated design patterns, content guidance, procurement conditions, tests and AI instructions. It checks whether completed tickets changed people's experience and coordinates reassessment across all six maturity dimensions. Executive leaders remain accountable for funding and implementing the resulting roadmap. \[1\]

## AI governance across business workflows

Maintain an inventory of AI-assisted workflows with a business owner, affected people, inclusion objectives, permitted actions, evidence requirements and escalation rules. The accessibility manager can steward the inclusion controls; engineering and business owners implement and operate them.

| **Control**              | **What the workflow should enforce**                                                                                                                                                                |
| ------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Approved knowledge       | Version the standards, component guidance, requirements, research methods and source material available to AI. Review updates and retain which versions informed a decision.                        |
| Bounded authority        | State when AI may draft, create tickets, open a change, start an approved survey, deploy or roll back. Prevent it from weakening requirements or disabling checks to make a task pass.              |
| Evidence and uncertainty | Separate observed failures, user reports and inferred causes. Retain source evidence and reproducible context. Route uncertain results for review rather than treating silence as success.          |
| Separation of controls   | Keep acceptance conditions and release controls outside the unilateral control of the agent generating the change. Require appropriate peer review and human evidence for non-automatable criteria. |
| Data boundaries          | Use only approved data and aggregates for the purpose agreed. Avoid inferring disability, detecting assistive technology for profiling, or joining anonymous feedback to customer accounts.         |
| Change and recovery      | Re-evaluate model, prompt, tool and dependency changes. Record decisions, monitor regressions and provide a human override and a workable rollback path.                                            |

### Apply the controls beyond software development

In recruitment and HR, evaluate whether screening, onboarding and employee systems support participation and an accessible route to human review. In procurement, require evidence about complete supplier workflows. In communications, check generated content, documents and media. In customer support, preserve alternative channels and escalation rather than optimising solely for automation rates.

Every business owner maps these controls into their own workflow, with the champions network identifying omissions and the programme coordinator maintaining organisational coverage. A generic AI policy cannot demonstrate that each operational workflow has effective controls.

### Make AI tickets actionable

Each ticket should retain the affected task and state, observed barrier, evidence source, applicable requirement or best-practice label, confidence, reproduction steps, acceptance conditions, assigned owner and verification method. Record the affected functional group only where supported by the evidence. Treat an AI-proposed cause as a hypothesis until checked.

Before closure, require technical verification and the planned outcome check. If a low-risk change can close automatically under approved rules, retain the evidence and enable sampling and reopening. AI must not close an issue merely because it generated a patch or the automated scan is clean.

## Continuous research and design optimisation

ASK AI by Accessiblethinking.com or a comparable accessible survey can provide recurring experience signals alongside technical tests. The supplied ASK overview describes six aspects: navigation, task completion, task time, content consumption, predictability and support for user preferences. It describes segmented, aggregated CSV results and survey setup through a unique URL or API key. \[5\]

Use EAA Annex I functional performance criteria as a lens for coverage and research questions. This is a proposed research application; a survey score is not an EAA conformity determination. Check needs beyond the survey's implemented segments, including vocal input, reach, photosensitivity and privacy. A comparison group reporting no particular need is not the randomised control arm of an experiment. \[4–5\]

| **Step**                     | **Management responsibility**                                                                                                                                                                                 |
| ---------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Detect and investigate       | AI combines permitted technical signals, support themes and aggregate UX results. Research and QA validate the signal and identify what is still unknown.                                                     |
| Launch the study             | The research lead defines approved questions, accessibility checks, triggers and recruitment. AI may create studies within these rules. Retain a stable core questionnaire and separate diagnostic questions. |
| Identify the version         | Record the journey, release, study period and experiment arm. Use distinct study identifiers or URLs for variants. Preserve exports before ending a study; do not join responses to personal profiles.        |
| Interpret the evidence       | The data lead checks response counts, recruitment, missingness, overlapping groups and the data available for uncertainty estimates. AI reports limitations alongside findings.                               |
| Develop remediation          | Design, content and engineering practitioners investigate causes and propose improvements. The product manager prioritises barriers using impact, obligations and evidence.                                   |
| Evaluate and retain learning | Verify technical requirements, repeat the outcome measures and assess group-level effects. Update shared patterns, tests and AI knowledge when an improvement is supported.                                   |

### Use experiments only where they can answer the question

Compare acceptable design options with predefined outcomes, allocation, observation periods and stopping rules. Do not retain a known blocking defect solely to create a control. Do not declare success from an overall average when a functional group worsens. With small samples, use targeted task research and describe quantitative results as inconclusive.

Aggregate means and total counts may not support reliable significance tests. Confirm that exports include the necessary distributions or uncertainty measures before claiming an A/B result. A before-and-after survey can show a change in reported experience, but does not by itself establish that the design caused it.

Reach people who abandon the journey or cannot use the survey through accessible support and research routes. Validate the actual ASK integration and schema before automating: the supplied documents differ in segment grouping and scale description. Off-site collection and aggregation support privacy, but do not alone establish compliance for every implementation.

## Deliver the AI Accessibility Maturity Model

Use the Double FW AI-Ready Accessibility Maturity Model as the organisational framework. It defines six dimensions and five levels. The responsibilities and evidence below are proposed ways to put that framework into practice; they do not add new official levels or a certification scheme. \[1\]

| **Dimension from the model**                 | **Suggested accountable owner**       | **Evidence of delivery**                                                                                                                         |
| -------------------------------------------- | ------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------ |
| Leadership and Governance                    | Sponsor                               | Funded commitments, named owners, executive decisions and an escalation route that works when inclusion conflicts with other priorities.         |
| Culture and Capability                       | Named workforce or capability lead    | Role-based learning, protected champion time, accessible employee participation and evidence that practitioners can apply the guidance.          |
| Design, Delivery, and Operations             | Named delivery or operations director | Requirements carried through procurement, architecture, design, QA, release, support and internal systems; recurring issues prevented at source. |
| Data, Measurement, and Comparable Experience | Named research or insight lead        | Customer and employee evidence, segment-level outcomes, support dependency, confidence and effort, with ethical collection and clear limits.     |
| AI, Automation, and Intelligent Systems      | Named AI governance owner             | AI inventory, inclusion evaluations, controlled permissions, human override, reviewed model changes and evidence of actual workflow outcomes.    |
| Ethics, Risk, and Organisational Trust       | Named risk or governance lead         | Inclusion impact decisions, transparent explanations, independent challenge, accessible redress and disabled people participating in governance. |

### Assess the whole organisation

The accessibility manager or designated programme coordinator maintains one evidence register spanning all six dimensions. Each dimension has a named owner, current evidence, gaps, planned action, funding and a review date. The sponsor owns the combined improvement roadmap. Product-level test results cannot establish organisational maturity on their own.

Use governance review, workshops, journey analysis, customer and employee insight, accessibility testing and AI system evaluation together. Include disabled people in deciding whether the evidence reflects comparable experience. Technical completion, satisfaction, autonomy, confidence and trust should remain visible as distinct outcomes.

### Make full delivery a continuing commitment

"Fully delivered" means the organisation has put all dimensions into operation and continues to test their effectiveness. It does not mean the highest level has been achieved by publishing a policy or completing a checklist. Review maturity as workflows, suppliers, models and user needs change; keep strengths and weaknesses visible rather than averaging away a weak dimension.

## Progression and management rhythm

| **Maturity level** | **What progression could look like in this embedded model**                                                                                                         |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1 Reactive         | Identify unowned barriers and establish who can act. Make current gaps visible; map AI already operating in customer and employee workflows.                        |
| 2 Foundational     | Fund owners, baseline requirements, common guidance, initial champion coverage and an evidence register. Pilot controlled research and AI permissions.              |
| 3 Operational      | Run accessibility through normal planning, procurement, development, QA and operations. Use recurring experience data and resolve identified barriers.              |
| 4 Integrated       | Connect product and business evidence with AI governance, shared patterns and executive decisions. Demonstrate that improvements survive across teams and releases. |
| 5 Transformative   | Enable disabled people to co-lead governance and improvement. Use AI responsibly to anticipate barriers and demonstrate sustained comparable participation.         |

The level names come from the maturity model. These examples are implementation guidance. Assess each dimension using evidence; do not infer a level from the number of tools deployed, champions recruited or tickets closed. \[1\]

### A suggested operating rhythm

- Every change: check affected requirements, AI permissions and test coverage. Decide whether the change needs a fresh study, manual assessment or additional challenge.
- Every sprint or delivery cycle: review blockers, incomplete evidence, scope changes and outcome signals. Assign actions and capacity; keep affected users visible in prioritisation.
- Monthly: the champions network reviews repeat issues, missed workflows and shared learning. Business owners review outcome gaps and ageing actions with the programme coordinator.
- Quarterly and after material change: the sponsor reviews all six maturity dimensions, funding, AI controls and customer and employee evidence. Refresh the improvement roadmap and commission challenge where needed.

### Measures that help managers act

Report requirement coverage and unresolved failures separately from task success, support dependency and experience scores. Track segment-level deterioration, the age and recurrence of barriers, and whether verified improvements have reached shared components or workflows. Pair every metric with its scope, denominator, period and known limits.

Governance measures should show whether champions have time and influence, whether escalations receive decisions, and whether accessibility requirements survive scope changes. AI measures should include unsupported conclusions, reopened tickets, regressions, overrides and the quality of the evidence retained.

### Start with a complete pilot

Choose one customer journey and one employee or operational workflow. Name the RACI owners, establish the baseline and test the escalation route. Run one full cycle from evidence to remediation and outcome evaluation. Use what failed in the process to improve the controls before extending the model across the organisation.

## Sources and interpretation

This guide proposes an operating model. Its RACI allocations, control examples and review rhythm are recommendations for adoption and adaptation. References establish the underlying standards, maturity framework and survey capabilities; they do not demonstrate that any particular organisation conforms or has reached a maturity level.

\[1\] Double FW Ltd. [AI Accessibility Maturity Model repository](https://github.com/Double-FW/AI-Accessibility-Maturity-Model)

Primary framework: [AI AMM.md at the reviewed repository revision](https://github.com/Double-FW/AI-Accessibility-Maturity-Model/blob/6ba3a9c3e9481a1edb349c0fbcfc23ecbbc6637c/AI%20AMM.md)

Reviewed 11 October 2026. Six dimensions and five level names are retained from the model. The framework emphasises comparable experience, governance, lived experience and continuous improvement.

\[2\] W3C. [Web Content Accessibility Guidelines 2.2](https://www.w3.org/TR/WCAG22/)

Use the applicable A and AA success criteria and conformance requirements. Scope includes full pages and complete processes. This guide does not replace criterion-level acceptance conditions or evidence.

\[3\] Deque Systems. [axe-core API documentation](https://github.com/dequelabs/axe-core/blob/develop/doc/API.md)

Version-specific guidance: [axe-core 4.13 rule guidance](https://dequeuniversity.com/rules/axe/4.13/)

Pin the actual 4.13.x package version used and retain the configured rule inventory. Include applicable WCAG A and AA rule tags through 2.2 and agreed best-practice rules; using only the tag for rules introduced in 2.2 would omit earlier coverage. Treat incomplete results as requiring review. Best-practice rules and manual evidence should retain their distinct classifications.

\[4\] Centre for Excellence in Universal Design, National Disability Authority. [Functional Performance Criteria](https://universaldesign.ie/communications-digital/european-accessibility-act/functional-performance-criteria)

Explains EAA Annex I, Section VII and its conditions of application. Research segmentation is a useful operational interpretation, not a replacement for determining applicable legal requirements. Privacy applies across accessible modes of use and should not be treated as a participant category.

\[5\] Accessiblethinking.com Supplied ASK AI Overview, ASK AI Survey Instructions, and ASK AI and the EAA materials, reviewed 11 October 2026.

The overview describes the six experience measures, segmentation, CSV delivery and URL/API-key setup. The instructions describe study operation and aggregation. The integration must resolve documented differences in scales and groupings before automated comparisons. No claim of universal survey accessibility, guaranteed anonymity, statistical significance or legal conformity is inferred from these materials.

### Working records to maintain

Keep the adopted RACI with named owners, requirement and evidence register, champions charter, workflow and AI inventory, survey and experiment register, release decisions, escalation log and maturity roadmap. Version the records so later decisions can be traced to the requirements, evidence and controls that applied at the time.
