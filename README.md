# TOGAF® EA Notes
---

## 1. What is TOGAF?

**TOGAF** (The Open Group Architecture Framework) is a globally recognised Enterprise Architecture (EA) framework. It provides a structured approach to designing, planning, implementing, and governing enterprise information architecture.

- Owned and maintained by **The Open Group**
- The current standard is the **10th Edition**
- Covers four architecture domains: **Business, Data, Application, Technology** (BDAT)

---

## 2. The Architecture Development Method (ADM)

The ADM is the core process of TOGAF — a cycle of phases used to develop and manage enterprise architecture.

### ADM Phases

| Phase | Name | Key Focus |
|---|---|---|
| **P** | Preliminary | "Setting up the Shop" — Capability Framework, principles, governance |
| **A** | Architecture Vision | Scope, stakeholders, business scenarios, high-level vision |
| **B** | Business Architecture | Business processes, capabilities, value streams |
| **C** | Information Systems Architectures | Data Architecture + Application Architecture |
| **D** | Technology Architecture | Technology components and platforms |
| **E** | Opportunities & Solutions | Solution Building Blocks (SBBs), roadmap options |
| **F** | Migration Planning | Transition Architectures, Implementation & Migration Plan (I&MP) |
| **G** | Implementation Governance | Oversight of solution delivery, compliance |
| **H** | Architecture Change Management | Monitoring change, managing re-iteration |
| **RM** | Requirements Management | Central hub connecting all phases |

### ADM Iterations

The ADM supports multiple types of iteration:

- **Architecture Capability Iteration** — revisiting the Preliminary phase
- **Architecture Development Iteration** — cycling through phases A–D
- **Transition Planning Iteration** — phases E–F
- **Architecture Governance Iteration** — phases G–H

### Reiteration & Change Types

| Change Type | Description | ADM Impact |
|---|---|---|
| **RE-Architecture** | Major structural change | Back to Phase A or Preliminary |
| **Large Incremental** | More than one phase rework | Multi-phase reiteration |
| **Simplification** | Small incremental change | Rework within a single phase |
| **General Change Management** | Ongoing governance activities | Phases G & H |

**Phase G** (Implementation Governance) handles: process reviews, audits, compliance assessments, disciplinary processes, dispensations, and exemptions.

**Phase H** (Architecture Change Management) handles: re-architecture, large incremental changes.

---

## 3. Architecture Scoping

Architecture scope is defined across three dimensions:

- **Breadth** — enterprise-wide vs. segment vs. capability-specific
- **Depth** — from contextual/conceptual down to technical/physical
- **Level** — which organisational or architectural layer is covered

### Four EA Engagement Contexts (DPBoK)

| Context | Level | EA Purpose |
|---|---|---|
| **Context I** | Capability Vision & Architecture Definition | EA to support **solution delivery** |
| **Context II** | Segment Vision & Architecture Definition | EA to support **project delivery** |
| **Context III** | Team of Teams | EA to support **portfolio management** |
| **Context IV** | Enduring Enterprise | EA to support **strategy** |

---

## 4. Architecture Abstraction Levels

TOGAF defines four abstraction levels that apply across ADM phases:

### Contextual
- Focuses on **why** the enterprise undertakes architecture work
- Defines scope, goals, drivers, and objectives
- Answers: *Why are we doing this?*

### Conceptual
- Decomposes requirements to understand the problem
- Uses **service models** (business, application, technology services)
- Answers: *What is needed?* — without prescribing how

### Logical
- Identifies the **kinds** of components needed (business, data, application, technology)
- Implementation-independent — multiple logical solution alternatives exist
- Answers: *How can the architecture be organised?*

### Physical
- Manages allocation and implementation of **physical components**
- Maps logical components to concrete technology choices
- Multiple physical alternatives may realise the same logical design

---

## 5. Architecture Building Blocks (ABBs & SBBs)

Building Blocks are reusable units of architecture capability.

### Types

| Type | Description |
|---|---|
| **ABB** (Architecture Building Block) | Logical/conceptual — defines what is needed |
| **SBB** (Solution Building Block) | Physical/specific — defines the actual solution component |

### Building Block Hierarchy (Example: Naval Vessel)

| Level | Example | Description |
|---|---|---|
| Level 1 | HMAS Hunter Class Frigate BB | Custom — Capability Specific |
| Level 2 | Frigate Stability Hull BB | Custom — Industry Specific |
| Level 3 | War Ship Engine BB | Custom — Common Systems Specific |
| Level 4 | Generic Foundation SBBs | Generic / Foundation — reusable base blocks |

### Key Principles

- Blocks can be **reused** from the Enterprise Continuum repository
- Blocks can be **composed** into Superblocks
- The goal is **SMART** Architecture Building Blocks — filtered to only those needed to realise the Target Architecture via the **Architecture Definition Document (A.D.D.)**

---

## 6. Key Deliverables & Artefacts

### Architecture Definition Document (A.D.D.)
The central deliverable that captures the architecture design — progresses through versions:
- **Draft 0.1** — initial baseline, conceptual, and domain architecture drafts
- **Approved Version 1.0** — finalised architecture

### Architecture Requirement Specifications (A.R.S.)
Spawned by Phase A; captured in the **Architecture Requirements Repository (ARR)**.

### Implementation & Migration Plan (I&MP)
Produced after finalising the A.D.D. — details the work packages, projects, and transition steps.

### Architecture Design & Definition Contracts
Agreements between architects and business stakeholders to govern delivery.

### Roadmap
Work packages (W/P) and projects organised across **Transition Architectures (T1, T2, T3…)**.

---

## 7. RAW vs. SAW

| Term | Meaning |
|---|---|
| **RAW** | Required Architecture Work — the full architecture scope |
| **SAW** | Scoped Architecture Work — the filtered, deliverable subset |

- RAW 1.0 may be iterated (RAW 1.1) due to exceptions or change requests
- SAW represents the realistic, approved scope for delivery
- **SLA BB** (Service Level Agreement Building Block) is defined during this scoping

---

## 8. Change Requests Driving ADM Cycles

New ADM cycles can be triggered by:

1. Request from Sponsor via EA team, market signals, etc.
2. Request from a business Stakeholder (top-down)
3. Discovery of opportunity by a Domain Architect (bottom-up)
4. Request from market, contractor, or partner
5. Environmental change (regulatory, technology shift, etc.)
6. Governance — ad hoc or continuous monitoring
7. Change to solution, implementation, or performance
8. Concerns backlog (Agile implementation context)

---

## 9. Phase E vs. Phase F Objectives

| Phase | Objective |
|---|---|
| **Phase E** | Identify candidate SBBs; check interoperability; identify conflicts or shared service opportunities; select compatible solutions |
| **Phase F** | Plan Transition Architectures; create the Implementation & Migration Plan; govern transition-based delivery |

Phase E uses the **Foundation/Common/System/Industry/Organisation-Specific** layering to assess SBB compatibility.

---

## 10. Transition Architecture Planning

Transition Architectures (T1, T2, T3…) represent intermediate target states:

- Each transition delivers a **complete BDAT** (Business, Data, Application, Technology) architecture slice
- Governed by **Implementation Governance (Phase G)**
- Builds progressively from baseline to full target state (100%)

### Build Patterns

| Pattern | Description |
|---|---|
| **Greenfield** | New build from scratch |
| **Quick Win / Achievable Target** | Near-term, lower-risk deliverables |
| **Mainstream** | Core enterprise transformation |
| **Reuse/Repeat** | Repeated pattern (e.g., "Plan once, build many" — Barracuda Class pattern) |

---

## 11. Agile EA vs. Traditional EA

### Agile or Not Agile? Decision Matrix

|  | Low Frequency of Delivery | High Frequency of Delivery |
|---|---|---|
| **High Degree of Change** | Infrastructure projects (e.g., airport, highway) | Agile SW development (CI/CD) |
| **Low Degree of Change** | Standard construction (e.g., residential building) | SW maintenance (continuous improvement) |

- **Predictive** approaches suit large infrastructure with low iteration
- **Agile/Iterative** approaches suit software-intensive, high-change environments
- **Transition-based delivery** bridges traditional and agile by planning multiple defined increments

---

## 12. Enterprise Security Architecture

Security is woven throughout the ADM:

- **Security Architecture Management** is a parallel track alongside Architecture Risk Management and Architecture Requirements Management
- Security considerations span all phases (A–H)
- Supports compliance tools: **ISM, ERM, ASCM**, etc.
- **Architecture Risks Catalogue** and **Architecture Risks Register** are maintained throughout

---

## 13. Repository & Enterprise Continuum

The **Architecture Repository** stores all architecture artefacts and enables reuse:

| Repository Component | Contents |
|---|---|
| Architecture Requirements Repository (ARR) | Architecture Requirement Specifications |
| Architecture Risks Catalogue | Identified risks |
| Architecture Risks Register | Tracked, active risks |
| Security Architecture Repository | Security artefacts |
| Enterprise Continuum | Classification of reusable building blocks |

**Reuse** from the repository is a key efficiency mechanism — blocks are classified and retrieved across ADM phases (A, B, C, D, E, F, G, H).

---

## 14. Business Scenarios

A **Business Scenario** is used in Phase A (and referenced throughout) to:

- Capture stakeholder concerns and drivers
- Define business, data, application, technology, and security requirements
- Involve the Architecture Team and business stakeholders collaboratively

---

## 15. TOGAF® EA Viewpoints Library (10th Edition)

The 10th Edition significantly expanded the viewpoints library. Key viewpoints by domain:

### Preliminary
- Principles Catalog, Stakeholder Catalog
- Value Chain Diagram, Solution Concept Diagram
- *(NEW)* Business Model Diagram, Business Capability Map, Value Stream Map

### Business Architecture
**Catalogs:** Organization/Actor, Driver/Goal/Objective, Role, Business Service/Function, Location, Process/Event/Control/Product, Contract/Measure, Business Capabilities, Value Stream, Value Stream Stages, Business Glossary *(NEW)*

**Matrices:** Business Interaction, Actor/Role, Value Stream/Capability, Strategy/Capability, Capability/Organization

**Diagrams:** Business Footprint, Business Service/Information, Functional Decomposition, Product Lifecycle, Goal/Objective/Business Service, Business Use-Case, Organization Decomposition, Process Flow, Business Event, Business Capability Map, Value Stream Map, Organization Map, Information Map

### Data Architecture
**Catalogs:** Data Entity/Data Component  
**Matrices:** Data Entity/Business Function, Application/Data  
**Diagrams:** Conceptual Data, Logical Data, Data Dissemination, Data Security, Data Migration, Data Lifecycle

### Application Architecture
**Catalogs:** Application Portfolio, Interface  
**Matrices:** Application/Organization, Role/Application, Application/Function, Application Interaction  
**Diagrams:** Application Communication, Application and User Location, Application Use-Case, Enterprise Manageability, Process/Application Realization, Software Engineering, Application Migration, Software Distribution

### Technology Architecture
**Catalogs:** Technology Standards, Technology Portfolio  
**Matrices:** Application/Technology  
**Diagrams:** Environments and Locations, Platform Decomposition, Processing, Networked Computing/Hardware, Network and Communications

### Requirements Management
- Requirements Catalog

### Opportunities & Solutions
- Project Context Diagram, Benefits Diagram

---

## 16. Foundation Metamodel

The **TOGAF Enterprise Metamodel** defines relationships between all architectural entities across the four domains.

### General Entities (Associated with All Objects)
`Principle` | `Constraint` | `Assumption` | `Requirement` | `Location` | `Gap` | `Work Package` → delivers → `Capability`

### Business Architecture Entities
- **Motivation**: Driver → Goal → Objective → Measure (Course of Action)
- **Organisation**: Actor, Organization Unit, Function, Role
- **Capability**: Business Capability, Value Stream
- **Process**: Process, Event, Control, Role, Business Service, Contract

### Cross-Domain Relationships
- **Business Service** → is automated by → **Application Service** → is implemented on → **Technology Service**
- **Data Entity** → resides in → **Logical Data Component** → realised by → **Physical Data Component**
- **Logical Application Component** → realised by → **Physical Application Component**
- **Logical Technology Component** → realised by → **Physical Technology Component**

---

## 17. Content Framework by ADM Phase

The content framework maps **metamodel levels** to ADM phases:

- **Phase A** — Contextual & Conceptual artefacts
- **Phases B, C, D** — Logical design artefacts (Architecture Design documents at v0.1)
- **Phases E, F** — Physical design, solution selection, roadmap
- **Phases G, H** — Governance and change management artefacts

### Metamodel Levels
| Level | Focus |
|---|---|
| **Level 1** | Foundation Metamodel — core entity types and relationships |
| **Level 2** | Extended Metamodel — additional relationships and domain-specific entities |

---

## 18. Classes of Architecture Engagement

TOGAF recognises different **classes of architecture change engagement** based on:

- **Why** the change is occurring
- **When / How frequently** it is needed
- **What** the scope and nature of the change is

These classes help determine which ADM phases to emphasise and how to tailor the engagement model for the organisation's context.
