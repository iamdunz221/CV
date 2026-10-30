# Nguyen Tien Dung | IT Business Analyst Portfolio

<div align="center">

![Role](https://img.shields.io/badge/Role-IT%20Business%20Analyst-blue?style=for-the-badge)
![University](https://img.shields.io/badge/FPT%20University-Software%20Engineering-orange?style=for-the-badge)
![Specialization](https://img.shields.io/badge/Specialization-AI%20Use%20Cases%20%26%20System%20Design-teal?style=for-the-badge)
![English](https://img.shields.io/badge/English-IELTS%205.5%20%7C%20TOEIC%20700%2B%20Target-green?style=for-the-badge)

**[📄 View Harvard-Format CV](CV_Nguyen_Tien_Dung_Business_Analyst.html)** | **[🌐 Interactive Web Portfolio](Portfolio_Nguyen_Tien_Dung.html)** | **[📫 Email Me](mailto:tiendunga2k13@gmail.com)**

</div>

---

## 👨‍💻 Executive Summary

I am a final-year **Software Engineering** student at **FPT University** (Expected 2027) pursuing an **IT Business Analyst** career path. By combining software architecture fundamentals with user-centric requirements engineering, I bridge the communication gap between business stakeholders and technical engineering teams.

- 🎓 **Education:** Bachelor of Science in Software Engineering, FPT University (GPA: 3.0 / 4.0).
- 🏆 **Honors:** Awarded **30% Academic Merit Scholarship** across all 4 undergraduate years.
- 🎯 **Core Strengths:** Requirements Elicitation, Agile User Stories (Gherkin AC), BPMN 2.0 Process Modeling, UML Architecture (Use Case, Sequence, Component Diagrams), and AI Use Case Feasibility Analysis.

---

## 🛠️ Core Competencies & Tool Stack

| Dimension | Methodologies & Technologies | Tools |
| :--- | :--- | :--- |
| **Requirements Engineering** | Stakeholder Elicitation, BRD, SRS (IEEE 830), Agile User Stories, Gherkin Acceptance Criteria, Scope Creep Control, Gap Analysis, UAT Validation | Jira, Confluence, Notion, Google Workspace |
| **Process & System Modeling** | BPMN 2.0, UML (Use Case, Activity, Sequence, Communication, Component, Package, Class Diagrams), ERD | Draw.io, Lucidchart, PlantUML |
| **Technical & AI Architecture**| 3-Tier Layered Architecture, Service-Oriented Architecture (SOA), Microservices, Netflix Eureka Service Discovery, RESTful API specifications, RBAC Security, BCrypt/Argon2 Cryptography | Postman (API Testing), PostgreSQL/MySQL, Docker basics |
| **UI/UX & Prototyping** | Low/High-Fidelity Wireframing, User Journey Mapping, Design-Dev Handoff | Figma, Stitch AI |

---

## 📂 Featured Case Studies

### 1. 🤖 Kidpro – Smart Preschool Management System (AI-Driven)
> **Role:** Business Analyst & QA Lead | **Timeline:** 4 Months | **Team Size:** 5 (Capstone Project)

#### The Business Problem
- **Boarding Meal Fee Disputes:** Daily morning roll-calls conducted manually on paper frequently caused billing discrepancies between parents and school accountants regarding absent-day fee deductions.
- **Child Pickup Safety Vulnerability:** Paper verification books at the school gate during peak dismissal hours posed security risks of unauthorized individuals picking up children.
- **Accountant Bottlenecks:** Reconciling attendance sheets with monthly tuition calculations required ~4 days of manual auditing per billing cycle.

#### BA Solution & Technical Deliverables
1. **AI Facial Recognition Attendance Specification:**
   - Specified an automated entrance camera workflow with dual-verification: validating the child's identity against the database while matching the accompanying guardian's registered facial profile.
   - Designed comprehensive **AI Edge Cases & Fallback Protocols**: Defined system behavior when confidence scores fall below **85%**, lighting conditions degrade, or an authorized alternate guardian is dispatched (prompting manual teacher verification with OTP/ID check).
2. **Automated Attendance-to-Billing Reconciliation:**
   - Designed daily batch-processing triggers where confirmed attendance records instantly adjust the student's monthly meal ledger, eliminating manual counting.
3. **Agile Documentation & Scope Management:**
   - Authored the complete **Software Requirements Specification (SRS)** and 40+ User Stories with Given-When-Then Acceptance Criteria; managed sprint backlogs in Jira to prevent scope creep.

#### Sample User Story (Gherkin Syntax)
```gherkin
Feature: Automated Meal Fee Accrual via AI Attendance
  As a School Accountant
  I want verified morning attendance logs to automatically adjust daily meal fee ledgers
  So that monthly invoice generation is 100% accurate without dispute investigations.

  Scenario: Verified Arrival before Cutoff Time
    Given student "Nguyen Bao An" is verified PRESENT via Gate AI Camera before 08:30 AM
    When the daily attendance batch job triggers at 09:00 AM
    Then the system accrues 1 daily boarding meal charge (45,000 VND) to the active invoice
    And emits an audit record with timestamp and verification snapshot reference.

  Scenario: Low Confidence Fallback (< 85%)
    Given an unrecognized guardian arrives at pickup
    When AI face match confidence returns 72% (< 85% threshold)
    Then the gate turnstile remains locked
    And the system routes an alert to the Duty Teacher app requesting physical ID verification.
```

#### Quantified Impact
- ⚡ **~60% reduction** in accountant invoice reconciliation time (from 4 days down to ~1.5 days).
- 🛡️ **Zero** meal calculation disputes across pilot testing.
- 🔒 **100% digital audit trail** established for all child pickup events.

---

### 2. 🏥 Hospital Management System (HMS) Architecture
> **Role:** Business Analyst & System Modeler | **Timeline:** 2 Months | **Team Size:** 5 | **Evaluation:** **9.8 / 10 Final Score**

#### The Business Problem
- **Departmental Fragmentation:** Paper-based patient routing between Outpatient Triage, Consultation Rooms, Diagnostic Labs, and Pharmacy created extensive wait times (~45 minutes per visit).
- **Scalability Barriers:** The legacy 3-Tier Layered Architecture could not handle distributed workloads when transitioning from a standalone clinic to a regional healthcare network with satellite branches.
- **Data Security Compliance:** Medical records (EMR) and billing transactions required stringent Role-Based Access Control (RBAC) and cryptographic integrity.

#### BA Solution & Technical Deliverables
1. **Clinical Workflow Re-engineering:**
   - Modeled streamlined patient journeys: `Appointment/Walk-in Triage -> Consultation & EMR Creation -> Lab Test Orders -> Electronic Prescribing -> Pharmacy Fulfillment -> Billing Settlement`.
2. **Architectural Evolution to SOA / Microservices:**
   - Collaborated with engineering leads to transition the monolithic core into distributed services (`Appointment Service`, `Medical Record Service`, `Billing Service`, `Pharmacy Service`).
   - Integrated the **Service Discovery Pattern using Netflix Eureka** and an API Gateway to dynamically register service instances, balance traffic loads, and ensure high availability.
3. **Comprehensive UML & Security Modeling:**
   - Delivered 86+ verified architectural diagrams including Sequence, Communication, Component, and Package diagrams.
   - Formalized 19 Business Rules (BR1 to BR19), upgrading password encryption standards from legacy hashing to **salted BCrypt / Argon2** and enforcing RBAC across 6 actor roles.

#### Architectural Overview (Netflix Eureka Service Discovery)
```text
[ Patient App / Doctor Web ]
              │
              ▼
       [ API Gateway ]  ◄───────►  [ Netflix Eureka Service Registry ]
              │                            (Heartbeat & Dynamic Lookup)
      ┌───────┼──────────────────────────────┐
      ▼       ▼                              ▼
[ Appointment ] [ Medical Record (EMR) ] [ Billing & Pharmacy ]
      │               │                      │
      └───────────────┼──────────────────────┘
                      ▼
            [ PostgreSQL Storage ]
       (ACID Transactions & RBAC Security)
```

#### Key Business Rules Formulated
- **BR2 (Role-Based Authorization):** System access strictly partitioned into 6 distinct roles (`Patient`, `Doctor`, `Nurse`, `Pharmacist`, `Cashier`, `System Admin`).
- **BR4 (Patient Visit Policy):** Supports both advance appointment scheduling and walk-in arrivals with automated triage urgency ranking.
- **BR19 (Cryptographic Protection):** User passwords must be hashed and salted using robust cryptographic algorithms (`BCrypt` / `Argon2`) prior to database persistence.

---

## 📜 BA Artifacts & Sample Deliverables

- **Requirements Specifications:** IEEE 830 SRS Document, Business Requirements Document (BRD).
- **Process Maps:** BPMN 2.0 Pool & Lane Diagrams for Outpatient & Kindergarten operations.
- **UI Prototypes:** Interactive Figma wireframes validating user flows prior to developer sprint handoff.
- **Quality Assurance:** UAT Test Plan, Traceability Matrix (RTM), and Defect Triage logs.

---

## 📬 Contact & Information

- **Name:** Nguyen Tien Dung (Nguyễn Tiến Dũng)
- **Location:** Hanoi, Vietnam
- **Email:** [tiendunga2k13@gmail.com](mailto:tiendunga2k13@gmail.com)
- **Phone:** (+84) 363 262 xxx
- **Education:** FPT University — Software Engineering (2023 - 2027)
- **Portfolio Repository:** [github.com/your-username/ba-portfolio](https://github.com)
