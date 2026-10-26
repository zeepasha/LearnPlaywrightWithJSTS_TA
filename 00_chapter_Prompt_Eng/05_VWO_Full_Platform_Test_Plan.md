# VWO Full-Platform Test Plan

> **Status:** Draft for review  
> **Highlight key:** **Confirmed** = stated in the supplied PRD or user input; **Proposed** = a test-planning recommendation requiring agreement; **Not provided** = information absent from the supplied material.

## 1. Test Plan ID and Title

| Field | Value |
| --- | --- |
| Plan ID | Locally assigned: TP-VWO-001 |
| Title | VWO Digital Experience Optimization Platform - Full-Platform Test Plan |
| Application | VWO (Visual Website Optimizer) |
| Product URL | https://app.vwo.com/ |
| Environment | QA; user confirmed that the stated product URL maps to the authorized QA environment. Exact tenant identifiers/details are **Not provided**. |
| Source | Product Requirements Document (PRD), prepared January 7, 2026; supplied PDF |
| Plan status | Draft; approval pending |

## 2. Objective and References

### Objective

Define a reviewable end-to-end test approach for the VWO platform described by the supplied PRD. The plan maps the PRD's functional requirements FR1-FR9 and non-functional requirements to planned test coverage. It is a test design artifact; no tests have been executed as part of creating it.

### RICE POT task inputs

| RICE POT element | Supplied value |
| --- | --- |
| Role | QA with 10 years of experience |
| Specialization | Functional and API testing; healthcare and insurance specialization supplied by user |
| Task | Test plan creation for VWO.com |
| Product domain | NA in the supplied prompt; the PRD describes a digital experience optimization platform |
| Feature scope | Full platform described in the PRD |
| Audience | QA, product, engineering, analytics, and business stakeholders; audience details otherwise **Not provided** |
| Deliverable | One Markdown test plan |
| Workflow | Guided; plan approval required; checkpoints at each major step |
| Formatting | Markdown headings, tables, and explicit status labels for highlighting |

The healthcare/insurance specialization is professional context only. It does not add healthcare requirements or regulations to the product scope. Privacy coverage below stays within the PRD's GDPR, CCPA, and regional data-policy statement.

### References and evidence limits

- Supplied VWO PRD, including product overview, user flows, functional requirements, non-functional requirements, KPIs, risks, and future enhancements.
- The PRD's general product and user descriptions are planning context; they do not define detailed acceptance criteria, API contracts, exact UI behavior, or test data.
- External product behavior has not been independently inspected or verified.

## 3. In Scope and Out of Scope

### In scope

- End-to-end functional testing of experimentation and testing: A/B, Split URL, and multivariate experiments, variations, audience targeting, goals/metrics, previews, scheduling, launch, monitoring, and result review (FR1, FR2, FR3, FR5, FR6; PRD user flow 5.1).
- Behavioral insights: click, scroll, and focus heatmaps; session recordings; surveys and feedback; funnel analytics; correlation of insights with experiments and prioritization (FR4; PRD user flow 5.2).
- Personalization by the PRD-listed geography, behavior, and demographic segments, including real-time tailored experiences (FR7).
- Integrations and data synchronization with the connectors named in the PRD, subject to environment availability (FR8).
- Program planning, collaboration, team tasks, and Kanban-style workflow (FR9).
- PRD-stated performance, security, scalability, data privacy, and reliability requirements.
- Relevant regression, integration, negative, boundary, and cross-browser/device checks where supported by environment and approved scope.

### Out of scope

- Unspecified features, business rules, and behaviors not present in the PRD or later approved acceptance criteria.
- Future enhancements: AI-driven suggestions, native mobile SDK enhancements, and predictive analytics/ROI forecasting.
- Penetration testing, formal compliance certification, and independent legal interpretation of privacy obligations.
- Pricing/licensing validation, unless separately requested; the PRD gives no testable pricing rules.
- Production execution. The stated target environment is QA; production access and authorization are **Not provided**.

### Scope constraints

- The supplied PRD is high-level. Detailed acceptance criteria, API specifications, supported browser/device matrix, workload profiles, and exact integration configurations are **Not provided**.
- The prompt says required application access is available and lists USER1, USER2, and Admin. Provisioned account details, role permissions, and 2FA setup are **Not provided**. No credentials or secrets are included in this plan.
- The healthcare/insurance specialization does not establish that healthcare data or HIPAA is in scope. No healthcare-specific regulatory tests are included.

## 4. Requirements and Planned Coverage

The functional requirement IDs FR1-FR9 are normalized from the PRD's formatted table. The PRD does not assign IDs to non-functional requirements; the NFR labels below are **locally assigned** for traceability.

| Requirement | Priority in PRD | Planned coverage | Key test conditions / evidence needed |
| --- | --- | --- | --- |
| FR1 - A/B, Split URL, and Multivariate Testing | Must | Create, configure, preview, schedule, launch, monitor, and conclude supported experiment types; verify multiple variations are represented in experiment configuration and reports. Include invalid/incomplete configuration and boundary variation counts after limits are supplied. | User confirmed FR1 acceptance criteria are **Not defined**. Variation limits, target pages, and safe QA traffic/test properties are **Not provided**. Keep scenarios at the PRD capability level; do not assert undocumented outcomes. |
| FR2 - SmartStats Engine | Must | Verify result reporting presents Bayesian analysis and supports the documented decision workflow; check result consistency against approved reference data or an approved statistical oracle. | User confirmed the winner decision rule is **Not defined**. Statistical methodology, reference datasets, and exact expected calculations are **Not provided**. Winner outcomes cannot be asserted without a decision rule. |
| FR3 - Visual and Code Editor | Must | Exercise visual/WYSIWYG experiment editing if available; validate save/preview behavior and editing-workflow response time against the PRD's 2-second target. Code-editor coverage is blocked because the requirement disposition is **Not defined**. | **Conflict:** PRD FR3 requires visual and code-editor/developer-level setup; user reports there are no code-editor workflows. Whether the PRD is outdated or the capability is unavailable in QA is **Not defined**. Visual-editor acceptance criteria, save semantics, error behavior, and timing measurement boundary are **Not provided**. |
| FR4 - Heatmaps and Session Recordings | Must | Verify capture and presentation of click, scroll, and focus interactions; plan session-recording, survey/feedback, and funnel scenarios from the product description. Validate collection against consent/privacy configuration once defined. | Capture eligibility, sampling, masking, retention, consent, and expected display rules are **Not provided**. |
| FR5 - Audience Targeting | High | Exercise behavior-based audience segmentation and targeting; include positive matches, non-matches, empty/invalid criteria, and boundary combinations after supported rule semantics are specified. | Detailed behavioral attributes, segment operators, precedence, and test visitor profiles are **Not provided**. |
| FR6 - Real-time Reporting and Dashboards | Must | Verify experiment analytics are refreshed and consistent across monitoring and reporting views; check filters, empty data, delayed data, and recovery behavior where defined. | Definition of "real-time," refresh targets, dashboard metrics, and reconciliation tolerance are **Not provided**. |
| FR7 - Personalization Engine | High | Exercise PRD-listed geography, behavior, and demographic segments; verify the configured tailored experience is delivered to a matching segment and not delivered to a non-matching segment, subject to approved rules. | Segment precedence, delivery latency target, fallback behavior, and approved synthetic profiles are **Not provided**. |
| FR8 - Integration Connectors | High | Plan connection, data synchronization, error/retry, duplicate/idempotency, and disconnect/recovery checks for enabled connectors named in the PRD, including Google Analytics, Mixpanel, Shopify, Salesforce, Segment, Snowflake, WordPress, and Drupal where available. | Enabled connector inventory, API contracts, sandbox accounts, mappings, rate limits, and synchronization schedules are **Not provided**. |
| FR9 - Collaboration and Workflow Management | Medium | Exercise planning, collaboration, team tasks, and Kanban-style experiment backlog workflows; verify role-based actions only after permissions are defined. | Workflow states, collaboration rules, notifications, audit expectations, and role permission matrix are **Not provided**. |
| NFR-PERF - Editing workflow performance (locally assigned) | Not stated | Measure applicable editing workflows against the PRD requirement of response within 2 seconds. | Timing start/end events, percentile/aggregation rule, hardware/network baseline, and workload are **Not provided**. |
| NFR-SEC - Security (locally assigned) | Not stated | Plan 2FA, role-based access control, and activity-log checks, including authorized/unauthorized role actions. | 2FA policy, role-permission matrix, log event schema, retention, and audit access are **Not provided**. |
| NFR-SCALE - Scalability (locally assigned) | Not stated | Plan controlled load/volume tests to assess behavior at high visitor volumes and monitor response/error/resource trends. | Definition of high volume, workload model, test limits, and acceptable performance degradation are **Not provided**. |
| NFR-PRIV - Data privacy (locally assigned) | Not stated | Plan checks against approved GDPR, CCPA, and regional data-policy requirements for collection, access, retention, deletion, and integration flows where applicable. | Applicable regions, data classifications, consent rules, retention/deletion periods, and approved compliance criteria are **Not provided**. |
| NFR-REL - Reliability (locally assigned) | Not stated | Plan availability/recovery evidence review against the PRD's 99.9% enterprise uptime SLA and verify documented service/monitoring evidence. | Measurement window, exclusions, service boundaries, recovery objectives, and testable QA environment equivalent are **Not provided**. |

### PRD success metrics (not acceptance thresholds)

The PRD lists conversion-rate improvement, experiments launched per quarter, engineering-time reduction, personalized-campaign engagement, and platform usability/NPS as business KPIs. Baselines, targets, measurement windows, and attribution rules are **Not provided**; these KPIs are not treated as pass/fail criteria in this plan.

---

**Checkpoint 1 complete:** Sections 1-4 establish the plan basis, scope, and traceability to all PRD functional and non-functional requirements.  
**Next:** Define test levels and types, environment/tooling/data prerequisites, and proposed entry/exit criteria. These will remain explicitly proposed or **Not provided** where the PRD lacks measurable detail.

## 5. Test Approach, Levels, and Types

### Approach

- Derive test scenarios from approved acceptance criteria for FR1-FR9 and the locally assigned NFR references. The PRD alone is not sufficiently detailed to define exact expected results for many behaviors.
- Prioritize end-to-end coverage of the PRD's experiment setup and behavioral-analysis user flows, then extend coverage to personalization, integrations, and workflow management.
- Use positive, negative, boundary, and recovery scenarios where the relevant behavior and limits are defined. Do not assert undocumented messages, limits, or business rules.
- Use synthetic or explicitly approved data. Do not place real customer, health, payment, or other sensitive data in test scenarios unless separately authorized and governed.
- Maintain requirement-to-test traceability and record blocked or deferred coverage with its reason.
- Run against an authorized QA environment only. Do not execute tests against production based solely on the product URL.

### Test levels

| Level | Planned use | Status / dependency |
| --- | --- | --- |
| API / service integration | Validate documented service contracts, authorization, payload validation, synchronization, and error handling for available APIs/connectors. | In scope as applicable; API specifications and access are **Not provided**. |
| System integration | Validate data flow between VWO modules and enabled third-party connectors, including consistency and recoverability. | In scope for configured integrations; connector inventory and sandboxes are **Not provided**. |
| End-to-end | Validate user-visible workflows from setup through launch, monitoring, insights, and result review; also cover personalization and planning workflows. | In scope; detailed acceptance criteria are **Not provided**. |
| Regression | Re-run approved smoke and risk-based scenarios after relevant changes to protect existing platform workflows. | Proposed; release cadence and regression suite are **Not provided**. |
| Unit / component | No direct unit-test execution is planned in this user-facing test plan. | Ownership and source-code test strategy are **Not provided**. |

### Test types

Functional, negative, boundary, integration, regression, compatibility, performance, scalability, security-control, privacy-control, and reliability evidence checks are planned only where applicable to requirements and supported by the approved environment. Penetration testing and formal compliance certification are excluded.

Compatibility testing should cover the approved browser, operating system, and device matrix. The PRD calls for cross-device/cross-browser QA but does not list supported targets; the matrix is **Not provided**.

## 6. Environment, Tools, Access, and Test Data

| Item | Plan / current information |
| --- | --- |
| Environment | QA, as supplied by the user. The exact environment name, tenancy, and its mapping to the stated URL are **Not provided**. |
| URL | https://app.vwo.com/; user confirmed this URL maps to the authorized QA environment. Test-data isolation and connector callback safety still require confirmation before execution. |
| Access | User states required application access is available. Account provisioning and environment authorization evidence are **Not provided**. |
| Roles | USER1, USER2, and Admin were supplied. Their permissions and test-account mapping are **Not provided**. |
| Authentication | PRD mentions 2FA. 2FA policy, test enrollment, recovery procedure, and whether all test accounts require it are **Not provided**. |
| Tools | Browser, API client, automation framework, test management, monitoring, and load-testing tools/versions are **Not provided**; select and approve them before execution. |
| Integrations | PRD names Google Analytics, Mixpanel, Shopify, Salesforce, Segment, Snowflake, WordPress, and Drupal, among other systems. Which are enabled in QA, plus sandbox credentials/configuration, are **Not provided**. |
| Test data | Use synthetic accounts, visitors, events, experiment variations, goals, segments, survey responses, and integration records. Specific datasets and reset procedures are **Not provided**. |
| Secrets | Do not store credentials or tokens in the plan or test code. Use the organization's approved secret-management mechanism; the mechanism is **Not provided**. |
| Privacy | Follow approved QA data handling and retention procedures. GDPR, CCPA, and regional obligations are named in the PRD, but detailed controls and test evidence are **Not provided**. |

Before execution, the environment owner should confirm that the target is an authorized QA tenant and that test traffic, data collection, and connector callbacks are safe and isolated from production users and systems.

## 7. Entry and Exit Criteria

The PRD does not define formal test entry/exit gates. The criteria below are **proposed for review**, not approved product requirements.

### Proposed entry criteria

- Product owner and QA approve the acceptance criteria for each in-scope FR and NFR, including expected results, limits, and known exclusions.
- QA environment owner confirms the URL, tenant, test-data isolation, connector sandboxes, and authorization to execute the planned tests.
- USER1, USER2, and Admin test accounts are provisioned, usable, and mapped to an approved role-permission matrix; required 2FA access is verified.
- Supported browser/device matrix, API specifications, integration inventory, and required tool versions are agreed and available for the tests that depend on them.
- Synthetic test data, data-reset approach, and privacy-safe logging/retention practices are approved.
- No known environment issue prevents execution of the planned smoke workflow; blockers and workarounds are documented.

### Proposed exit criteria

- Every approved in-scope requirement has at least one linked test or an explicitly approved waiver/deferment; traceability status is recorded.
- All scheduled tests have a recorded outcome, and blocked, deferred, and not-run cases are identified with reasons. No unexecuted test is reported as passed.
- No open release-blocking defect remains, using the severity/triage policy approved for this effort; that policy is **Not provided** and must be agreed before this gate is applied.
- Functional, integration, compatibility, and security-control deviations are reviewed and accepted or assigned follow-up owners.
- For the defined editing workflows, measured response time meets the PRD's 2-second requirement under an agreed workload and measurement method; those details are **Not provided**.
- Scalability and privacy exit decisions use approved workload and compliance criteria; neither is inferable from the high-level PRD alone.
- Reliability sign-off records evidence against the 99.9% enterprise uptime SLA and its agreed measurement window. A short QA run alone is not sufficient to establish the SLA.
- QA and product owners review residual risks, exceptions, and the test summary before approval.

## 8. Roles, Responsibilities, Estimates, and Schedule

The PRD names stakeholder groups but does not assign individuals, accountable owners, or dates. The responsibilities below are **proposed** and require confirmation.

| Role | Proposed responsibility | Named owner / availability |
| --- | --- | --- |
| QA lead / test owner | Maintain plan and traceability; coordinate execution; report results, blockers, and residual risk. | **Not provided** |
| Product owner / business representative | Clarify acceptance criteria, priorities, KPI interpretation, and approve scope and exceptions. | **Not provided** |
| Engineering / API team | Provide API specifications, build details, technical support, defect analysis, and fixes. | **Not provided** |
| DevOps / environment owner | Confirm QA tenant, access, deployment/build information, monitoring, data isolation, and environment readiness. | **Not provided** |
| Analytics / CRO specialist | Define experiment metrics, SmartStats expected evidence, and analytics reconciliation criteria. | **Not provided** |
| Integration owner | Identify enabled connectors, sandbox access, mappings, and external-system dependencies. | **Not provided** |
| Security / privacy owner | Confirm 2FA/RBAC controls, approved data handling, regional privacy criteria, and evidence sources. | **Not provided** |

### Proposed sequence (dates and estimates not provided)

1. Confirm acceptance criteria, requirements traceability, test data, tools, roles, and environment authorization.
2. Prepare QA tenant, accounts, synthetic data, connector sandboxes, and smoke checks.
3. Execute functional and API/integration checks, followed by cross-browser/device and regression coverage.
4. Execute approved performance, scalability, security-control, privacy-control, and reliability evidence checks.
5. Triage defects, perform targeted retests/regression, document residual risk, and obtain sign-off.

Calendar dates, effort estimates, release/build cadence, and team availability are **Not provided**. Do not infer a delivery timeline until these are agreed.

## 9. Defect Management and Reporting

### Defect record

Record, at minimum: defect ID; linked PRD requirement or locally assigned NFR reference; title; environment and build; preconditions; synthetic test data; reproducible steps; expected and actual results; evidence; severity and priority; status; owner; and retest result. Do not include secrets or real personal data in evidence.

### Triage and reporting

- Use the organization's defect tracker and workflow; tool, status values, severity scale, priority scale, and service-level targets are **Not provided**.
- **Proposed:** hold defect triage each execution day while active testing is underway; include QA, product, and engineering representatives as available. Confirm or change this cadence before execution.
- **Proposed:** provide a concise daily status during active execution, including planned/executed/blocked tests, defects by agreed severity, requirement coverage, environment issues, and key risks.
- Assign severity and priority using an approved convention. Until one is supplied, label assessments as proposed and avoid treating them as confirmed release gates.
- Retest fixes in the target build and run risk-based regression for affected workflows. Preserve the original result and link the retest evidence; do not overwrite a failed result as though it never occurred.

## 10. Risks, Dependencies, Assumptions, and Open Questions

| Type | Item | Impact | Proposed action / status |
| --- | --- | --- | --- |
| PRD risk | Technical complexity; PRD mitigation: robust SDKs, documentation, and pre-built templates. | Setup and integration paths may be difficult to exercise consistently. | Confirm supported setup paths and documentation/build versions before test design is baselined. |
| PRD risk | Data accuracy; PRD mitigation: SmartStats and cross-tool validation integrations. | Incorrect or inconsistent results could undermine experiment decisions. | Agree statistical oracle/reference data and cross-tool reconciliation tolerances; currently **Not provided**. |
| PRD risk | User adoption; PRD mitigation: guided tours, in-app support, and analyst assistance. | Adoption and usability risks may not be exposed by functional checks alone. | Use the PRD's usability/NPS KPI only with an agreed study method and threshold; both are **Not provided**. |
| Dependency | QA tenant data isolation and connector callback safety. | Shared data or callbacks could affect real users or production systems. | URL-to-QA mapping is confirmed by the user; environment owner must still confirm isolation and safe test traffic before execution. |
| Dependency | Role permissions, test accounts, and 2FA. | RBAC and security scenarios cannot be validated without defined roles and access. | Obtain the approved permission matrix and test account setup; **Not provided**. |
| Dependency | Acceptance criteria and API contracts. | Exact expected results and API assertions cannot be designed from the high-level PRD alone. | Obtain approved functional criteria and API specifications for applicable areas. |
| Dependency | Enabled integrations and external sandboxes. | Connector coverage may be blocked or unsafe without controlled third-party endpoints. | Confirm QA connector inventory and sandbox credentials/configuration through approved secret handling. |
| Dependency | Browser/device matrix and workload model. | Compatibility, performance, and scalability conclusions may be incomplete. | Agree supported targets, visitor-volume profile, and measurement boundaries before execution. |
| Unverified assumption | USER1, USER2, and Admin accounts can be used in QA. | Role-based test coverage depends on provisioned accounts. | User stated access is available; actual account readiness and permissions remain **Not defined**. |
| Confirmed by user | Product URL `https://app.vwo.com/` maps to the authorized QA environment. | This confirms the URL/environment mapping only; it does not establish data isolation or connector safety. | Retain environment-owner checks for isolation, safe test traffic, and connector callbacks before execution. |
| Scope decision | Healthcare/insurance specialization does not make healthcare regulations applicable to this product. | Adding HIPAA or other unstated regulations would expand scope beyond the PRD. | Stay with PRD privacy scope: GDPR, CCPA, and regional data policies. |

### Unresolved details (Not defined)

- FR3 conflict disposition: **Not defined**. PRD FR3 requires code-editor/developer setup, while the user reports no code-editor workflows. Code-editor coverage remains blocked; no source-of-truth decision is assumed.
- Approved acceptance criteria and detailed behaviors for FR1-FR9: **Not defined** beyond the high-level PRD descriptions.
- QA test-data isolation, safe test traffic, and connector callback safety: **Not defined**; the product URL's mapping to the authorized QA environment is confirmed.
- USER1, USER2, and Admin permission mapping, account setup, and 2FA procedure: **Not defined**.
- QA API specifications, enabled integrations/connectors, third-party sandboxes, supported browsers, devices, and operating systems: **Not defined**.
- SmartStats methodology/reference data, real-time reporting target, performance measurement method, scalability workload, and reliability measurement window: **Not defined**.
- Privacy controls, data categories, applicable regions, consent behavior, retention, and deletion criteria: **Not defined** beyond the PRD naming GDPR, CCPA, and regional policies.
- Test tools, defect tracker, named owners, schedule, severity/priority conventions, and reporting cadence: **Not defined**.

## 11. Suspension and Resumption Criteria

The following criteria are **proposed** and require approval before execution.

### Suspend testing when

- The environment owner cannot confirm QA authorization, or the target appears to be production or a shared environment without approved isolation.
- A significant environment outage, deployment instability, or dependency failure prevents reliable execution or invalidates results.
- Test data or connector activity risks affecting real users, production systems, or unapproved personal data.
- A blocking defect prevents a core workflow from being tested, or observed behavior makes further results unreliable.
- Required acceptance criteria, access, or safety controls are missing for a high-risk test.

### Resume testing when

- The environment owner confirms authorization, stability, and data isolation; affected dependencies are available.
- Blocking defects are fixed or an approved workaround is documented, and a relevant smoke check passes.
- Test data is reset or reconciled as required, and accounts/access are revalidated.
- QA and the relevant product/engineering owners agree that the original test results remain valid or identify which tests must be rerun.

Record suspension and resumption time, reason, affected requirements/tests, owner, evidence, and rerun decision in the execution record.

## 12. Test Deliverables and Approval

### Deliverables

- This test plan and its approved revisions.
- Requirement-to-test traceability and the approved test scenarios/cases.
- Environment, data, and execution records, including blocked and not-run tests.
- Defect records and retest/regression evidence.
- Test summary with coverage status, results, open defects, exceptions, residual risks, and approval status.
- Performance, scalability, privacy, security-control, and reliability evidence where those activities are approved and performed.

### Approval

| Approver | Approval responsibility | Name / status |
| --- | --- | --- |
| Product owner | Confirms scope, acceptance criteria, priorities, and business-risk acceptance. | **Not provided / Pending** |
| QA lead | Confirms plan coverage, readiness, execution summary, and residual QA risks. | **Not provided / Pending** |
| Engineering / environment owner | Confirms technical readiness, environment authorization, and dependency status. | **Not provided / Pending** |
| Security / privacy owner | Confirms applicable security/privacy criteria and evidence expectations. | **Not provided / Pending** |

**Plan state:** Draft for review; approval has not been recorded. This document defines planned testing only. No test execution, build validation, compliance assessment, or production-readiness determination is claimed.

**Checkpoint 3 complete:** Sections 8-12 complete the proposed ownership, schedule sequence, defect process, risks, suspension/resumption gates, deliverables, and approval record.

## Final Review Checklist

- [x] Scope covers the full platform requirements FR1-FR9 and the PRD's non-functional requirements.
- [x] Healthcare-specific compliance was not added; privacy scope stays with the PRD.
- [x] Missing criteria, access details, tools, thresholds, owners, and dates are marked **Not provided** or **Proposed**.
- [x] Functional and non-functional requirements are mapped to planned coverage.
- [x] Planned work is distinguished from executed testing and verified results.
- [x] Test plan sections follow the supplied RICE POT Test Plan profile.
- [ ] Stakeholder review and approval completed.