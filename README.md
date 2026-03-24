# TOGAF® EA — Visual Study Notes

![TOGAF](https://img.shields.io/badge/TOGAF®-10th%20Edition-E05D26?style=flat-square) ![Standard](https://img.shields.io/badge/Standard-The%20Open%20Group-1A4A8A?style=flat-square) ![Diagrams](https://img.shields.io/badge/Diagrams-v3.0%20%7C%202025-2E7D32?style=flat-square)

> Based on the **TOGAF® Standard, 10th Edition** 

---

## Table of Contents

| # | Section | Key Concept |
|:--|---------|-------------|
| 1 | [What is TOGAF?](#1-what-is-togaf) | Framework overview & four domains |
| 2 | [The ADM Cycle](#2-the-architecture-development-method-adm) | Core phases, iterations, change types |
| 3 | [Architecture Scoping](#3-architecture-scoping) | Breadth, depth, level & EA contexts |
| 4 | [Abstraction Levels](#4-architecture-abstraction-levels) | Contextual → Conceptual → Logical → Physical |
| 5 | [Building Blocks](#5-architecture-building-blocks-abbs--sbbs) | ABBs, SBBs, hierarchy |
| 6 | [Key Deliverables](#6-key-deliverables--artefacts) | A.D.D., I&MP, Roadmap |
| 7 | [RAW vs. SAW](#7-raw-vs-saw) | Scoping & filtering architecture work |
| 8 | [Change Requests](#8-change-requests-driving-adm-cycles) | Eight triggers for new ADM cycles |
| 9 | [Phase E vs. F](#9-phase-e-vs-phase-f-objectives) | Opportunities vs. Migration Planning |
| 10 | [Transition Architecture](#10-transition-architecture-planning) | T1 → T2 → T3 build patterns |
| 11 | [Agile EA](#11-agile-ea-vs-traditional-ea) | Decision matrix |
| 12 | [Security Architecture](#12-enterprise-security-architecture) | Security across the ADM |
| 13 | [Repository & Continuum](#13-repository--enterprise-continuum) | Reuse & storage |
| 14 | [Business Scenarios](#14-business-scenarios) | Capturing requirements |
| 15 | [Viewpoints Library](#15-togaf-ea-viewpoints-library-10th-edition) | Catalogs, matrices, diagrams |
| 16 | [Foundation Metamodel](#16-foundation-metamodel) | Entity relationships |
| 17 | [Content Framework](#17-content-framework-by-adm-phase) | Metamodel levels by phase |
| 18 | [Classes of Engagement](#18-classes-of-architecture-engagement) | Why / when / what |

---

## 1. What is TOGAF?

**TOGAF** (The Open Group Architecture Framework) provides a structured approach to designing, planning, implementing, and governing enterprise information architecture.

```mermaid
mindmap
  root((TOGAF))
    Framework
      Owned by The Open Group
      10th Edition Current
      Globally recognised standard
    Four Domains
      Business
      Data
      Application
      Technology
    Core Components
      ADM Cycle
      Architecture Repository
      Enterprise Continuum
      Viewpoints Library
      Foundation Metamodel
```

---

## 2. The Architecture Development Method (ADM)

The ADM is the **core iterative process** of TOGAF — a structured cycle of phases for developing and managing enterprise architecture.

### ADM Phase Flow

```mermaid
flowchart TB
    RM(["Requirements\nManagement\nCentral Hub"])

    P["P · Preliminary\n'Setting up the Shop'\nCapability Framework\nPrinciples & Governance"]
    A["A · Architecture Vision\nScope & Stakeholders\nBusiness Scenarios\nHigh-level Vision"]
    B["B · Business Architecture\nProcesses & Capabilities\nValue Streams"]
    C["C · Information Systems\nData Architecture\nApplication Architecture"]
    D["D · Technology Architecture\nTechnology Components\nPlatforms"]
    E["E · Opportunities & Solutions\nCandidate SBBs\nRoadmap Options"]
    F["F · Migration Planning\nTransition Architectures\nImplementation & Migration Plan"]
    G["G · Implementation Governance\nOversight of Delivery\nCompliance"]
    H["H · Architecture Change Mgmt\nMonitor Change\nManage Re-iteration"]

    P --> A --> B --> C --> D --> E --> F --> G --> H --> A
    RM <--> A & B & C & D & E & F & G & H
```

### ADM Iteration Types

```mermaid
flowchart LR
    subgraph CAP ["Architecture Capability Iteration"]
        P2[Preliminary]
    end
    subgraph DEV ["Architecture Development Iteration"]
        A2[A] --> B2[B] --> C2[C] --> D2[D]
    end
    subgraph TRANS ["Transition Planning Iteration"]
        E2[E] --> F2[F]
    end
    subgraph GOV ["Architecture Governance Iteration"]
        G2[G] --> H2[H]
    end

    CAP --> DEV --> TRANS --> GOV
    GOV -->|"Re-iterate"| DEV
```

### Reiteration & Change Types

| Change Type | Description | ADM Impact |
|---|---|---|
| **RE-Architecture** | Major structural change | Back to Phase A or Preliminary |
| **Large Incremental** | More than one phase rework | Multi-phase reiteration |
| **Simplification** | Small incremental change | Rework within a single phase |
| **General Change Management** | Ongoing governance | Phases G & H |

> **Phase G** handles: process reviews, audits, compliance assessments, disciplinary processes, dispensations, exemptions.
>
> **Phase H** handles: re-architecture decisions, large incremental changes.

---

## 3. Architecture Scoping

Architecture scope is defined across **three dimensions**:

```mermaid
flowchart LR
    B["BREADTH
    ―――――
    Enterprise-wide
    Segment
    Capability-specific"]

    D["DEPTH
    ―――――
    Contextual
    Conceptual
    Logical
    Physical / Technical"]

    L["LEVEL
    ―――――
    Organisational layer
    Architectural layer
    Initiative level"]

    B --- D --- L
```

### Four EA Engagement Contexts (DPBoK)

```mermaid
flowchart BT
    C1["CONTEXT I
    Capability Vision & Architecture Definition
    EA to support Solution Delivery"]

    C2["CONTEXT II
    Segment Vision & Architecture Definition
    EA to support Project Delivery"]

    C3["CONTEXT III
    Team of Teams
    EA to support Portfolio Management"]

    C4["CONTEXT IV
    Enduring Enterprise
    EA to support Strategy"]

    C1 --> C2 --> C3 --> C4

    style C1 fill:#FCE4EC,stroke:#880E4F,color:#000
    style C2 fill:#FFF3E0,stroke:#E65100,color:#000
    style C3 fill:#E8F5E9,stroke:#2E7D32,color:#000
    style C4 fill:#E3F2FD,stroke:#1565C0,color:#000
```

---

## 4. Architecture Abstraction Levels

TOGAF defines **four abstraction levels** that apply across all ADM phases:

```mermaid
flowchart TD
    CTX["CONTEXTUAL
    Why are we doing this?
    Environment, goals, drivers, objectives
    Scope of architecture work"]

    CON["CONCEPTUAL
    What is needed?
    Service models — business, application, technology
    Requirement decomposition"]

    LOG["LOGICAL
    How can architecture be organised?
    Kinds of components needed
    Implementation-independent"]

    PHY["PHYSICAL
    With what is it realised?
    Allocation of physical components
    Concrete technology choices"]

    CTX --> CON --> LOG --> PHY

    style CTX fill:#FFF3E0,stroke:#E65100,color:#000
    style CON fill:#E8F5E9,stroke:#2E7D32,color:#000
    style LOG fill:#E3F2FD,stroke:#1565C0,color:#000
    style PHY fill:#F3E5F5,stroke:#6A1B9A,color:#000
```

| Level | Key Question | Primary ADM Use |
|---|---|---|
| **Contextual** | Why? | Phase P & A — scope & motivation |
| **Conceptual** | What? | Phase A & B — service models |
| **Logical** | How organised? | Phases B, C, D — architecture design |
| **Physical** | With what? | Phases E & F — solution realisation |

---

## 5. Architecture Building Blocks (ABBs & SBBs)

Building Blocks are **reusable, composable units** of architecture capability.

### ABB vs. SBB

```mermaid
flowchart LR
    ABB["ABB
    Architecture Building Block
    ―――――――――――
    Logical / Conceptual
    Defines WHAT is needed
    Reused from Enterprise Continuum"]

    SBB["SBB
    Solution Building Block
    ―――――――――――
    Physical / Specific
    Defines HOW it is built
    Actual solution component"]

    ABB -->|"realised by"| SBB

    style ABB fill:#E3F2FD,stroke:#1565C0,color:#000
    style SBB fill:#F3E5F5,stroke:#6A1B9A,color:#000
```

### Building Block Hierarchy (Naval Vessel Example)

```mermaid
flowchart TD
    L1["LEVEL 1 — Capability Specific
    HMAS Hunter Class Frigate BB"]

    L2["LEVEL 2 — Industry Specific
    Frigate Stability Hull BB"]

    L3["LEVEL 3 — Common Systems Specific
    War Ship Engine BB"]

    L4["LEVEL 4 — Generic Foundation SBBs
    Reusable base blocks"]

    L1 --> L2 --> L3 --> L4

    style L1 fill:#FFEBEE,stroke:#B71C1C,color:#000
    style L2 fill:#FFF3E0,stroke:#E65100,color:#000
    style L3 fill:#E8F5E9,stroke:#1B5E20,color:#000
    style L4 fill:#E3F2FD,stroke:#0D47A1,color:#000
```

### Key Principles

- Blocks are **reused** from the Enterprise Continuum repository
- Blocks can be **composed** into Superblocks
- Goal: **SMART** Building Blocks — filtered to only what is needed to realise the Target Architecture via the **A.D.D.**

---

## 6. Key Deliverables & Artefacts

```mermaid
timeline
    title Architecture Deliverable Lifecycle
    section Phase A
        Business Scenario        : Stakeholder concerns & driver analysis
        A.R.S. Draft             : Architecture Requirements Specifications
    section Phases B to D
        A.D.D. v0.1              : Baseline architecture & domain designs
    section Phases E to F
        A.D.D. v1.0 Approved     : Finalised architecture
        Roadmap                  : Work packages across T1 T2 T3
        I&MP                     : Implementation & Migration Plan
    section Phases G to H
        Design Contracts         : Architect–Stakeholder agreements
        Governance Reports       : Compliance assessments & audits
```

| Deliverable | Phase | Purpose |
|---|---|---|
| **A.R.S.** — Architecture Requirements Specs | A | Capture requirements per phase |
| **A.D.D.** — Architecture Definition Document | A–D | Central architecture design record |
| **I&MP** — Implementation & Migration Plan | F | Work packages, projects, transition steps |
| **Architecture Design & Definition Contracts** | G | Govern delivery between architects & business |
| **Roadmap** | F | Work packages organised across T1, T2, T3 |

---

## 7. RAW vs. SAW

```mermaid
flowchart LR
    RAW["RAW 1.0
    Required Architecture Work
    ―――――――――
    Full architecture scope
    All candidate components"]

    FILTER{{"Filter &
    Scope"}}

    SAW["SAW
    Scoped Architecture Work
    ―――――――――
    Approved deliverable subset
    SMART Building Blocks only"]

    EXCEPT["Exception /
    Change Request"]

    RAW2["RAW 1.1
    Updated scope"]

    RAW --> FILTER --> SAW
    FILTER -->|"Exception found"| EXCEPT --> RAW2

    style RAW fill:#FFF3E0,stroke:#E65100,color:#000
    style SAW fill:#E8F5E9,stroke:#2E7D32,color:#000
    style RAW2 fill:#FFF3E0,stroke:#E65100,color:#000
```

> **SLA BB** (Service Level Agreement Building Block) is defined during RAW → SAW scoping.

---

## 8. Change Requests Driving ADM Cycles

New ADM cycles can be triggered by **eight sources**:

```mermaid
flowchart TD
    ADM(["New ADM Cycle"])

    T1["1. Sponsor / EA Team
    Market signals"]
    T2["2. Business Stakeholder
    Top-down request"]
    T3["3. Domain Architect
    Bottom-up opportunity"]
    T4["4. Market / Contractor
    or Partner"]
    T5["5. Environmental Change
    Regulatory / technology shift"]
    T6["6. Governance
    Ad hoc or continuous monitoring"]
    T7["7. Solution / Implementation
    Performance change"]
    T8["8. Concerns Backlog
    Agile implementation context"]

    T1 & T2 & T3 & T4 & T5 & T6 & T7 & T8 --> ADM
```

---

## 9. Phase E vs. Phase F Objectives

```mermaid
flowchart LR
    subgraph E ["Phase E — Opportunities & Solutions"]
        E1["Identify candidate SBBs"]
        E2["Check interoperability"]
        E3["Identify conflicts or
        shared service opportunities"]
        E4["Select compatible solutions"]
        E1 --> E2 --> E3 --> E4
    end

    subgraph F ["Phase F — Migration Planning"]
        F1["Plan Transition Architectures
        T1 to T2 to T3"]
        F2["Create I&MP"]
        F3["Govern transition-based delivery"]
        F1 --> F2 --> F3
    end

    E --> F
```

Phase E uses the **SBB Compatibility Stack** to assess solutions:

```
Foundation  →  Common  →  System  →  Industry  →  Organisation-Specific
```

---

## 10. Transition Architecture Planning

Transition Architectures (T1, T2, T3…) are **intermediate target states** between baseline and full target.

```mermaid
gantt
    title Transition Architecture Delivery — BDAT Slices
    dateFormat  X
    axisFormat  T%s

    section Business
    Baseline       :done,    b0, 0, 1
    T1 Business    :active,  b1, 1, 4
    T2 Business    :         b2, 4, 7
    T3 Target      :         b3, 7, 10

    section Data
    Baseline       :done,    d0, 0, 1
    T1 Data        :active,  d1, 1, 4
    T2 Data        :         d2, 4, 7
    T3 Target      :         d3, 7, 10

    section Application
    Baseline       :done,    a0, 0, 1
    T1 App         :active,  a1, 1, 4
    T2 App         :         a2, 4, 7
    T3 Target      :         a3, 7, 10

    section Technology
    Baseline       :done,    t0, 0, 1
    T1 Tech        :active,  t1, 1, 4
    T2 Tech        :         t2, 4, 7
    T3 Target      :         t3, 7, 10
```

### Build Patterns

| Pattern | Description | Example |
|---|---|---|
| **Greenfield** | New build from scratch | New platform deployment |
| **Quick Win** | Near-term, lower-risk | Achievable first increment |
| **Mainstream** | Core enterprise transformation | Primary delivery stream |
| **Reuse / Repeat** | Plan once, build many | Barracuda Class pattern |

---

## 11. Agile EA vs. Traditional EA

```mermaid
quadrantChart
    title Project Candidate Selection — Agile or Predictive?
    x-axis Low Frequency of Delivery --> High Frequency of Delivery
    y-axis Low Degree of Change --> High Degree of Change
    quadrant-1 AGILE SW Development CI/CD
    quadrant-2 Infrastructure Projects e.g. Airport
    quadrant-3 SW Maintenance Continuous Improvement
    quadrant-4 Standard Construction e.g. Residential
    Agile SW: [0.85, 0.85]
    Airport: [0.2, 0.8]
    SW Maintenance: [0.8, 0.2]
    Construction: [0.2, 0.2]
```

| Approach | Best For | ADM Style |
|---|---|---|
| **Predictive** | Large infrastructure, low iteration | Full ADM cycle, single pass |
| **Agile / Iterative** | Software-intensive, high-change | Incremental ADM iterations |
| **Transition-based** | Bridge between both | Multiple defined increments T1, T2, T3 |

---

## 12. Enterprise Security Architecture

Security is a **parallel track** woven throughout the entire ADM — not a separate phase.

```mermaid
flowchart LR
    subgraph ADM ["ADM Phases"]
        A2[A] --> B2[B] --> C2[C] --> D2[D] --> E2[E] --> F2[F] --> G2[G] --> H2[H]
    end

    subgraph SEC ["Security Architecture Track"]
        SM["Security Architecture
        Management"]
        RC["Architecture Risks
        Catalogue"]
        RR["Architecture Risks
        Register"]
        SM --> RC --> RR
    end

    subgraph COMP ["Compliance Tools"]
        ISM["ISM"]
        ERM["ERM"]
        ASCM["ASCM"]
    end

    ADM <--> SEC
    SEC --> COMP
```

---

## 13. Repository & Enterprise Continuum

```mermaid
flowchart TD
    REPO[("Architecture
    Repository")]

    ARR["Architecture Requirements
    Repository — ARR
    ―――――
    Architecture Requirement
    Specifications"]

    RC["Architecture Risks
    Catalogue
    ―――――
    Identified risks"]

    RR["Architecture Risks
    Register
    ―――――
    Tracked, active risks"]

    SAR["Security Architecture
    Repository
    ―――――
    Security artefacts"]

    EC["Enterprise
    Continuum
    ―――――
    Classified reusable
    Building Blocks"]

    REPO --> ARR & RC & RR & SAR & EC

    EC -->|"Reuse across phases A B C D E F G H"| REUSE["Building Block
    Reuse"]

    style REPO fill:#1A4A8A,stroke:#1A4A8A,color:#fff
    style REUSE fill:#E8F5E9,stroke:#2E7D32,color:#000
```

---

## 14. Business Scenarios

A **Business Scenario** is used in Phase A (and referenced throughout) to translate stakeholder concerns into architecture requirements.

```mermaid
flowchart LR
    TEAM["Architecture Team
    + Business Stakeholders"]

    TEAM --> BS["Business
    Scenario"]

    BS --> BR["Business
    Requirements"]
    BS --> DR["Data
    Requirements"]
    BS --> AR["Application
    Requirements"]
    BS --> TR["Technology
    Requirements"]
    BS --> SR["Security
    Requirements"]

    BR & DR & AR & TR & SR --> ARS["Architecture
    Requirement
    Specifications
    A.R.S."]

    style BS fill:#1A4A8A,stroke:#1A4A8A,color:#fff
    style ARS fill:#2E7D32,stroke:#2E7D32,color:#fff
```

---

## 15. TOGAF® EA Viewpoints Library (10th Edition)

The 10th Edition significantly expanded the viewpoints library across five architecture domains.

```mermaid
flowchart TD
    VL["TOGAF Viewpoints Library — 10th Edition"]

    VL --> PREL["PRELIMINARY
    ―――――
    Catalogs: Principles · Stakeholder
    Diagrams: Value Chain · Solution Concept
    NEW: Business Model · Business Capability Map · Value Stream Map"]

    VL --> BIZ["BUSINESS ARCHITECTURE
    ―――――
    Catalogs: Org/Actor · Driver/Goal · Role · Location · Value Stream · Business Glossary NEW
    Matrices: Business Interaction · Strategy/Capability · Value Stream/Capability
    Diagrams: Business Footprint · Process Flow · Business Event · Org Map · Info Map"]

    VL --> DATA["DATA ARCHITECTURE
    ―――――
    Catalogs: Data Entity/Component
    Matrices: Data Entity/Business Function · Application/Data
    Diagrams: Conceptual Data · Logical Data · Data Security · Data Lifecycle"]

    VL --> APP["APPLICATION ARCHITECTURE
    ―――――
    Catalogs: Application Portfolio · Interface
    Matrices: App/Organization · Role/Application · App/Function
    Diagrams: Application Communication · App Use-Case · Software Engineering"]

    VL --> TECH["TECHNOLOGY ARCHITECTURE
    ―――――
    Catalogs: Technology Standards · Technology Portfolio
    Matrices: Application/Technology
    Diagrams: Environments/Locations · Platform Decomposition · Network/Communications"]

    style PREL fill:#FFF3E0,stroke:#E65100,color:#000
    style BIZ fill:#E8F5E9,stroke:#2E7D32,color:#000
    style DATA fill:#E3F2FD,stroke:#1565C0,color:#000
    style APP fill:#F3E5F5,stroke:#6A1B9A,color:#000
    style TECH fill:#FCE4EC,stroke:#880E4F,color:#000
```

### Viewpoint Types Explained

| Type | Purpose | Examples |
|---|---|---|
| **Catalogs** | Inventories of architecture elements | Org/Actor Catalog, Technology Portfolio |
| **Matrices** | Cross-domain relationships | Application/Technology Matrix |
| **Diagrams** | Visual representations of architecture | Process Flow, Platform Decomposition |

---

## 16. Foundation Metamodel

The **TOGAF Enterprise Metamodel** defines relationships between all architectural entities.

### General Entities (cross-domain)

```mermaid
flowchart LR
    P[Principle] & C[Constraint] & A[Assumption] & R[Requirement] & L[Location] & G[Gap] --> WP[Work Package]
    WP -->|"delivers"| CAP[Capability]
```

### Business Architecture Entities

```mermaid
flowchart TD
    DRV[Driver] -->|"Creates"| GOAL[Goal]
    GOAL -->|"Made specific by"| OBJ[Objective]
    OBJ -->|"Tracked against"| MEAS[Measure]
    DRV -->|"Motivates"| COA["Course of Action"]
    OBJ -->|"Realises"| COA

    PROD[Product] & ORG["Organisation Unit"] --> BC["Business Capability"]
    BC -->|"Is operationalised by"| VS["Value Stream"]
    ACT[Actor] -->|"Performs task in"| PROC[Process]
    PROC -->|"Produces"| BS["Business Service"]
    BS -->|"Governed by"| CON[Contract]

    style DRV fill:#FFF3E0,stroke:#E65100,color:#000
    style GOAL fill:#FFF3E0,stroke:#E65100,color:#000
    style OBJ fill:#FFF3E0,stroke:#E65100,color:#000
    style MEAS fill:#FFF3E0,stroke:#E65100,color:#000
```

### Cross-Domain Relationships

```mermaid
flowchart LR
    subgraph BIZ ["Business Architecture"]
        BS2["Business Service"]
    end

    subgraph APP ["Application Architecture"]
        AS["Application Service"]
        LAC["Logical Application Component"]
        PAC["Physical Application Component"]
        LAC -->|"realised by"| PAC
    end

    subgraph DATA ["Data Architecture"]
        DE["Data Entity"]
        LDC["Logical Data Component"]
        PDC["Physical Data Component"]
        DE -->|"resides in"| LDC -->|"realised by"| PDC
    end

    subgraph TECH ["Technology Architecture"]
        TS["Technology Service"]
        LTC["Logical Technology Component"]
        PTC["Physical Technology Component"]
        LTC -->|"realised by"| PTC
    end

    BS2 -->|"automates"| AS
    AS -->|"implemented on"| TS

    style BIZ fill:#E8F5E9,stroke:#2E7D32,color:#000
    style APP fill:#F3E5F5,stroke:#6A1B9A,color:#000
    style DATA fill:#E3F2FD,stroke:#1565C0,color:#000
    style TECH fill:#FCE4EC,stroke:#880E4F,color:#000
```

---

## 17. Content Framework by ADM Phase

```mermaid
flowchart LR
    subgraph CONTEXT ["Contextual & Conceptual"]
        PA["Phase A
        Architecture Vision
        Business Scenarios
        A.R.S. spawned"]
    end

    subgraph LOGICAL ["Logical Design — v0.1 Drafts"]
        PB["Phase B
        Business Architecture"]
        PC["Phase C
        Data & Application"]
        PD["Phase D
        Technology Architecture"]
        PB --> PC --> PD
    end

    subgraph PHYSICAL ["Physical Design & Roadmap"]
        PE["Phase E
        Opportunities & Solutions
        SBB selection"]
        PF["Phase F
        Migration Planning
        I&MP and Roadmap"]
        PE --> PF
    end

    subgraph GOVERNANCE ["Governance & Change"]
        PG["Phase G
        Implementation Governance
        Compliance"]
        PH["Phase H
        Change Management
        Re-iteration"]
        PG --> PH
    end

    CONTEXT --> LOGICAL --> PHYSICAL --> GOVERNANCE

    style CONTEXT fill:#FFF3E0,stroke:#E65100,color:#000
    style LOGICAL fill:#E3F2FD,stroke:#1565C0,color:#000
    style PHYSICAL fill:#E8F5E9,stroke:#2E7D32,color:#000
    style GOVERNANCE fill:#F3E5F5,stroke:#6A1B9A,color:#000
```

### Metamodel Levels

| Level | Focus |
|---|---|
| **Level 1** — Foundation Metamodel | Core entity types and relationships across all four domains |
| **Level 2** — Extended Metamodel | Additional relationships and domain-specific entities |

---

## 18. Classes of Architecture Engagement

TOGAF recognises different **classes of architecture change engagement**, determined by three questions:

```mermaid
flowchart TD
    WHY{"WHY is the
    change occurring?"}

    WHEN{"WHEN / HOW OFTEN
    is it needed?"}

    WHAT{"WHAT is the
    scope & nature?"}

    WHY --> CLASS["Class of Architecture Engagement"]
    WHEN --> CLASS
    WHAT --> CLASS

    CLASS --> EMP["Which ADM phases
    to emphasise"]
    CLASS --> TAIL["How to tailor
    the engagement model"]
    CLASS --> GOV2["Governance
    approach"]

    style CLASS fill:#1A4A8A,stroke:#1A4A8A,color:#fff
```

The engagement class determines how the ADM is applied — from lightweight advisory work through to full enterprise re-architecture.

---
