# Generic (super detailed) prompt for analyzing a system project description PDF

> **How to use:** paste this prompt into an AI chat and **attach the PDF** (or paste the text extracted from the PDF).  
> **Objective:** generate a complete analysis (product + requirements + architecture + risks) and an **estimated backlog in hours** by discipline (UX/UI, Front-end, Back-end, Integration, QA).

---

## INSTRUCTIONS FOR THE AI

You are a **Software Architect + Product Analyst + Tech Lead + PO**.  
Analyze the provided PDF (system project description) and produce an **extremely detailed**, structured, and actionable response.

### Rules and Quality
1. **Base your analysis only on the PDF content**. When something is not explicit, **state that it is an inference** and explain why.
2. List **assumptions** separately and mark them as **(ASSUMPTION)**.
3. List **questions/doubts** separately and mark them as **(DOUBT)**.
4. If there are contradictory passages, record them as **(CONFLICT)** and propose a resolution.
5. Use clear language with examples. For non-technical audiences, include a summarized version.
6. Whenever possible, generate **artifacts**: lists, tables, flows, acceptance criteria, risk matrix, backlog, estimates.
7. If the PDF does not have enough detail, still produce a complete result with:
   - what can be safely affirmed,
   - what needs to be defined,
   - and a “minimum viable” backlog to validate the project (MVP).

---

## EXPECTED OUTPUT (mandatory format)

### 0) Analysis Metadata
- Project name (if any):
- Version/date of the document (if any):
- Author/organization (if any):
- Context (1–2 sentences):
- PDF completeness degree (0–100%):
- Quick list of critical gaps (bullet points):

---

# 1) Project Overview (What the project is)
Explain:
- **Problem** the project solves
- **Value proposition**
- **Expected benefits**
- **Main functionalities (high level)**
- **What the project is NOT** (if there are indications)

Include:
- Summary for **non-technical** (max. 10 lines)
- Summary for **technical** (max. 10 lines)

---

# 2) Business Goals and KPIs
Identify and detail:
- Business goals (cost reduction, efficiency gain, scale, compliance, etc.)
- Suggested metrics/KPIs (even if not explicit) with:
  - KPI definition
  - How to measure
  - Collection frequency
  - Suggested initial target (ASSUMPTION if necessary)

Examples of KPIs (adjust to the PDF context):
- Average time per operation
- Rework reduction
- Error rate
- Active adoption (DAU/MAU) if it's a product
- Response time / performance

---

# 3) Target Audience, Personas, and Roles (RBAC)
Map:
- Who uses the system (internal/external)
- Personas / user profiles
- Roles and permissions (RBAC), including:
  - What each profile can see/do
  - Data restrictions (e.g., multitenancy, sensitive data)

**Output:**
- Table: Persona | Goal | Pain Points | Key Functionalities | Permissions

---

# 4) Scope (In Scope / Out of Scope) + Phases (MVP vs Future)
Produce:
- What is **In Scope**
- What is **Out of Scope**
- Division by phases:
  - **MVP (Phase 1)**
  - **Phase 2**
  - **Phase 3 / Future Roadmap**

**Output:**
- List prioritized by impact x effort (if possible)
- Indication of what is a dependency/risk

---

# 5) Educational Analogy (for quick understanding)
Create **2–3 analogies** to explain the system to:
1) non-technical person  
2) technical team  
3) business stakeholder  

Each analogy must contain:
- “This is like…”
- Mapping of elements (e.g., “user = customer”, “flow = conveyor belt”, etc.)
- Limitations of the analogy (where it fails)

---

# 6) System Journeys and Flows (User Flows)
Extract and/or derive:
- Main flows (happy path)
- Alternative flows
- Exception/error flows
- System states (e.g., “draft”, “published”, “canceled”)

**Mandatory Output:**
- List of flows with numbered steps
- For each flow: input, output, rules, validations, user messages
- If possible: a text pseudo-diagram (e.g., Mermaid block - optional)

---

# 7) Functional Requirements (FR)
List and detail:
- Requirements per module
- Associated business rules
- Validations
- Permissions
- Expected results

**Output:**
- Table: ID | Requirement | Description | Priority (MoSCoW) | Dependencies | Observations

---

# 8) Non-Functional Requirements (NFR) — mandatory
Identify and propose (if not in the PDF):
- Performance (p95, p99, throughput, latency)
- Scalability (horizontal/vertical)
- Availability (SLA)
- Security (authentication, authorization, OWASP, encryption, GDPR/compliance)
- Observability (logs, metrics, tracing)
- Audit (audit trail)
- Usability (accessibility, responsiveness)
- Compatibility (browsers, mobile, etc.)
- Maintainability and testability
- Backup/restore and retention
- Internationalization/locale (if applicable)

**Output:**
- Table: Category | Requirement | How to validate/test | Level (MVP/Future) | Observations

---

# 9) System Structure (how it will be structured)
Describe clearly:
- Module view (e.g., Admin, Operations, Reports, Settings, Integrations)
- Components (front, back, database, cache, queues, storage)
- Bounded Contexts if it makes sense
- Internal dependencies

**Output:**
- Map of modules + responsibilities
- List of internal/external APIs per module (if applicable)

---

# 10) Technical Architecture (suggested or implicit)
Explain:
- Architectural style (modular monolith, microservices, event-driven, etc.)
- Patterns (Clean Architecture, DDD, CQRS, etc.)
- Communication (REST, gRPC, messaging)
- Data strategy (SQL/NoSQL, cache, indexes)
- State strategy (stateless, sessions)
- Deploy strategy (containers, CI/CD)

**Output:**
- Textual architecture drawing (components and connections)
- List of architectural decisions with pros/cons (summarized ADR)

---

# 11) Domain and Data Model (Entities)
Extract or propose:
- Main entities
- Relevant fields
- Relationships
- Integrity rules
- Enums/status

**Output:**
- Data dictionary (table per entity)
- Business rules per entity
- Suggested tables/indexes (if appropriate)

---

# 12) External Integrations and Contracts
Map:
- External systems (ERP, gateways, authentication, etc.)
- Integration type (REST/SOAP, webhook, queue)
- Integration authentication/security
- Data exchanged (input/output)
- Errors and retries
- SLA and limits (rate limit)

**Output:**
- Table: Integration | Goal | Method | Auth | Payload | Errors | Observations

---

# 13) Authentication, Authorization, and Compliance (GDPR/LGPD)
Detail:
- Login/SSO (if any)
- RBAC/ABAC (access rules)
- Sensitive data and access policy
- GDPR: legal basis, consent, retention, anonymization (if applicable)

**Output:**
- Matrix: Profile x Permission x Module
- List of GDPR risks and mitigation

---

# 14) Audit, Logs, and Traceability
Define:
- What should be audited (critical actions)
- Minimum record structure (who, when, what, before/after)
- Retention and search requirements
- Observability (structured logs, metrics, tracing)

**Output:**
- Checklist of auditable events
- Example of audit event (illustrative JSON)

---

# 15) Acceptance Criteria and Definition of Done
For the main requirements, produce:
- Acceptance criteria (Given/When/Then)
- Definition of Done (DoD) per task type (UX/FE/BE/QA)

**Output:**
- List of criteria per key requirement
- DoD Checklist

---

# 16) Impediments, Observations, and Dependencies
Extract:
- Explicit impediments from the PDF
- Technical/business dependencies
- Restrictions (deadline, technology, legacy, team, compliance)

**Output:**
- Prioritized list (impact)
- Proposed mitigations

---

# 17) Project Risks (matrix)
Create a matrix with:
- Risk
- Probability (Low/Medium/High)
- Impact (Low/Medium/High)
- Severity (PxI)
- Mitigation
- Contingency plan

---

# 18) Task Backlog (super detailed) + Hourly Estimates per Discipline
Create a backlog organized by epics and stories, with:
- **Epics**
- **Features**
- **User Stories** (format: “As a [persona], I want [action], so that [benefit]”)
- **Technical tasks** (FE/BE/Infra)
- **Acceptance criteria**
- **Dependencies**
- **Riscos**
- **Estimate in hours** separated by:
  - UX/UI
  - Front-end
  - Back-end
  - Integration (between front and back / contracts / adjustments)
  - QA

### Estimation Rules
- State if it is a **conservative** or **aggressive** estimate
- Always state assumptions (ASSUMPTION)
- Separate MVP vs Future (if possible)
- Identify items that need a **spike** (technical research)

**Mandatory Output:**
1) **Backlog table**  
   - ID | Epic | Story/Task | Description | Dependencies | Acceptance Criteria | UX | FE | BE | INT | QA | Total | Observations

2) **Summary by discipline**  
   - Total UX (h)
   - Total Front-end (h)
   - Total Back-end (h)
   - Total Integration (h)
   - Total QA (h)
   - Grand Total (h)

3) **Summary by phase**
   - MVP (h) + items
   - Phase 2 (h) + items
   - Phase 3 (h) + items

---

# 19) Release Plan and Validation Strategy
Propose:
- Release 0 (discovery): prototype + validation
- Release 1 (MVP): minimum value
- Release 2+: expansion

Include:
- What to measure in each release (KPIs)
- How to collect feedback (analytics, interviews, logs)

---

# 20) Final Questions (essential doubts)
List the **10–20 most important questions** to close the scope and reduce risk, for example:
- What is the SLA?
- Which integrations are mandatory for the MVP?
- Who approves rules/flows?
- Is there multitenancy?
- What data is subject to GDPR?
- Volume of users/requests?

---

## PRESENTATION FORMAT
- Use **numbered headings** exactly as above.
- Use tables where indicated.
- Be detailed but objective: prioritize what changes decisions.
- If the document contains confusing terms, create a **glossary** at the end.

---

## BONUS (optional, if appropriate given the PDF content)
### A) Glossary of terms
### B) Suggested list of ADRs (architectural decisions)
### C) Draft list of endpoints per module
### D) CRUD Matrix per entity and module
