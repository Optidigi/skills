---
name: saas-planning-baseline
description: >-
  Create or explicitly revise a SaaS product-planning baseline and engineering
  handoff from requirements, decisions and evidence. Use for product discovery,
  initial architecture, feasibility planning, or a requested planning refresh.
  Do not use for ordinary coding, CI repair, routine delivery, reviewing this
  skill, unrelated business plans, or executing the plan.
---

# SaaS planning baseline

Produce a concise baseline that a repository-attached engineering owner can inspect, qualify and execute. Support product discovery and planning in a web agent or local agent. Preserve the user's intended offering and existing decisions; distinguish confirmed requirements, proposed choices and untested assumptions.

## Establish the starting point

Read supplied requirements, examples and existing authoritative docs. In an existing project, use current source/refs when accessible and identify superseded instructions; avoid silently replacing contracts or recommending a rewrite. State which evidence and tools are accessible. A shared link, remembered connection or installed MCP does not establish access to its contents or operations.

Ask only questions whose answers materially change purpose, scope, feasibility or authority. Group them into a small set. Continue independent preparation while answers are pending. Label other unknowns and offer recommendations instead of inventing owner decisions. Reuse existing authorization; preparation is not a reason to request it again.

## Define the product before prescribing the implementation

Capture users and their jobs, supported conditions, required journeys, features and domain properties, business rules, exclusions, UI/reference expectations and observable acceptance. Include representative success and failure examples. State relevant money, ownership, privacy, lifecycle and reliability constraints; apply them to this product rather than importing a generic checklist.

Separate:

- **Requirements:** user/provider obligations that the implementation must satisfy.
- **Decisions:** agreed choices, their reasons and who may change them.
- **Proposals:** recommended choices not yet adopted; identify a decision owner where approval is actually required.
- **Hypotheses:** assumptions still requiring observation, with the effect of failure.

For external claims, distinguish documented capability from observed project behavior; record the source and applicable conditions.

Propose the simplest supported stack and responsibility boundaries that fit. Prefer platform-supported defaults unless a concrete requirement justifies divergence. Leave ordinary implementation details to the engineering owner. A plausible design is not proof of platform feasibility.

## Resolve the risks that could invalidate the offering

Research load-bearing claims against current primary sources when browsing is available. Record the exact platform/version/distribution context, source, known restriction and cheapest executable proof. Verify sources by opening them, not relying on snippets. Date unstable facts; label unavailable evidence.

For each important uncertainty, specify the observation needed, allowed environment, required access, success/failure criterion and decision affected. Assign a probe to the local owner when the planning host cannot run it. Mock success cannot qualify an external contract.

Specify the minimum scaffold or vertical slice the local owner needs to obtain the proof. Do not plan substantial dependent commitments or declare a dependent capability ready while its load-bearing assumption remains unproved. A pending proof blocks the affected commitment or acceptance, not the bounded experiment needed to resolve it. Continue independent preparation; implementation remains for the local owner to execute only when authorized.

## Plan a connected path and its expansion

Define the smallest real user journey that crosses the critical boundaries, then order the remaining features around expanding it. End at user value, including the asynchronous processing, durable state and downstream access needed to deliver it—not merely the last screen or API call. Include necessary provider setup, deployment and observability early enough to exercise it. A page-only skeleton is insufficient for a product that depends on authentication, persistence, billing or another integration.

For each increment name the outcome, dependencies, acceptance evidence and unresolved obligations. Apply relevant safety controls as soon as the corresponding access, data or external effects exist, including during development experiments. Distinguish local engineering completion, native/provider qualification and release readiness; name substituted or unqualified boundaries. Keep all required features visible; a thin first path does not remove later requirements.

## Prepare the local handoff

Use [assets/baseline-template.md](assets/baseline-template.md) to assemble the result; combine or omit inapplicable sections. Usually produce one portable Markdown baseline plus a copyable startup prompt. Reuse repository documentation conventions if files are requested. Save only to an authorized destination; otherwise return the document in chat.

Identify who does what:

- The owner sets product commitments, resource/permission limits and consequential acceptance.
- One local engineering owner qualifies the environment and owns the authorized outcome across implementation, testing, review, integration, permitted development deployment and runtime qualification, including directly necessary corrections in existing components.
- Fresh supporting agents answer bounded research/review questions; their use depends on host support and useful independent scope.
- A separate planning agent assists with consequential decisions or unresolved assumptions without becoming a mandatory relay for every slice.

Define the authorized outcome and completion boundary. Direct the local owner to continue after ordinary integration and return for agreed outcome acceptance, a genuine blocker, or a decision/effect outside existing authority—not merely an internal work-item boundary. Preserve actual milestone restrictions and required approvals in an existing project.

Name development resources, permitted operations, spending/production limits and missing inputs. Reuse valid grants within their scope; neither the plan nor a startup prompt creates permission or credentials.

Name capabilities needed for the next path, then suggest actual tools only where available. A CLI/API may suffice without an MCP. Browser access must support inspecting the relevant app. Identify missing secrets by purpose and private entry method, never include their values.

Recommend skills selectively: research for uncertainty; writing-for-agents for agent documents; TDD for behavior; diagnosing-bugs for reproduced defects; code-review for independent review; handoff for continuity. These are examples, not required dependencies. The local owner inspects each selected skill's trigger, provenance and instructions before use and checks duplicates/conflicts. During setup or relevant changes, verify effective configuration, loaded versions and runtime capabilities where observable; report limits instead of inventing verification. Recommend deliberate compatible updates with qualification and rollback, not automatic migration to the newest release.

Set expectations for meaningful behavior/boundary tests, runtime/browser checks, proportionate independent review and applicable final-candidate CI. For TDD changes, observe the expected failing behavior before implementation; research, prose and inspection need no artificial RED. After corrections, recheck affected behavior, integrate, and verify the integrated build in the allocated environment. Exercise affected native boundaries when needed—not every expensive scenario for unrelated edits. Preserve repository-required gates; avoid arbitrary test ratios, fixed model mandates and universal full-review resets.

Supporting briefs specify scope, context/refs, ownership and output. Reviewers challenge the author's conclusions against acceptance and interacting implementation, distinguish inspection from personally executed checks, and report actual isolation. The engineering owner reconciles results. Do not describe sequential self-review as independent review when the host lacks separate contexts.

Keep product, decisions, plan, setup and current state discoverable in the repo. A short AGENTS entry point routes to them. Update affected docs with behavior changes; keep current refs, verified progress, unresolved obligations and resume steps compact. Prompts express intent; actual host/provider permissions and an actual runtime control execution and persistence.

## Check completeness and report readiness

Before handoff, check that required journeys/features have acceptance conditions, load-bearing assumptions have evidence or assigned probes, the first path is connected, and authority/resource boundaries are explicit or marked pending. Resolve contradictions within existing authority; present genuine product conflicts for owner decision with a recommendation.

Report whether the baseline is ready for local qualification, which product decisions are pending, and which dependent work requires proof/access. Do not claim verified environment, owner approval or launch readiness without evidence. Provide the startup prompt using only authority actually granted; use labeled permission choices when not yet granted.

Keep the result proportional to the project. Use the template as a coverage guide, not a form requiring every heading. For a small product, aim for roughly 800–1,200 words plus the startup prompt; expand only for material complexity. State each rule once and reference it from acceptance/worklist rows rather than repeating it in prose. This skill prepares work; installing tools, creating resources, changing a repository or deploying remains governed by the user's actual request and permissions.
