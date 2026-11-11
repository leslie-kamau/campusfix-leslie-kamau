Multimedia university of Kenya
Leslie Kamau
Sct-253-012/2022
campusfix-leslie-kamau/
├── README.md
├── week1/
│   └── problem-statement.md
├── week2/
│   └── model-justification.md
└── week3/
    └── srs-draft.md
    # Week 1: Problem Statement & Stakeholder Analysis

## 1. Problem Statement
In a university environment, facilities faults—such as broken computers, damaged laboratory lights, leaking water pipes, faulty classroom doors, and malfunctioning projectors—frequently occur. Currently, these issues are reported through informal, fragmented channels including verbal complaints, WhatsApp messages, emails, or paper forms

This lack of structured reporting creates significant operational issues
* **Lack of Visibility:** Difficulty determining which faults remain unresolved or are recurring.
* **No Prioritization:** Inability to identify and escalate urgent issues efficiently.
* **Unclear Accountability:** Ambiguity regarding who is assigned to fix specific problems.
* **Untracked Service Levels:** Inability to measure wait times or verify if maintenance meets expected response times

CampusFix closes this gap by providing a centralized digital platform to track facilities problems from initial report to verified resolution

## 2. Stakeholder Analysis
| Stakeholder Role | Description & Needs | Primary System Goals |
| :--- | :--- | :--- |
| **Students & Teaching Staff** | Report campus facilities issues (e.g., broken equipment, leaks). | Fast reporting, real-time status updates, and confirmation of fixes. |
| **Triage / Admin Staff** | Review incoming reports, assess urgency, and assign tasks. | Easy request triage, priority management, and staff assignment. |
| **Maintenance Staff** | Receive assigned tasks, perform repairs, and update status. | Task queue management, status updating, and resolution logging. |
| **University Management** | Oversee overall campus maintenance and response times. | Performance metrics, service level tracking, and recurring fault reports

## 3. System Scope
CampusFix is designed as a focused software prototype demonstrating an end-to-end software engineering process

* **In Scope:**
  * User authentication for reporting and administrative management.
  * Fault reporting interface with category and location selection.
  * Triage module for priority assignment and staff routing.
  * Maintenance portal for task tracking and status updates.
  * Resolution confirmation and ticket closure
* **Out of Scope:**
  * Hardware/IoT integration for automated fault detection.
  * Complex procurement or inventory/financial billing software integration.
  * # Week 2: Software Process Model & Individual Project Plan

## 1. Software Process Model Justification
For the initial individual phase and subsequent prototype development of CampusFix, an **Agile (Scrum/Iterative)** process model is selected.

### Justification:
1. **Incremental Refinement:** CampusFix starts as an individual foundation and evolves into a team project with expanding requirements (e.g., change requests, refactoring). An iterative process supports progressive additions without requiring fixed, static initial designs.
2. **Early Prototyping:** Agile emphasizes delivering functional modules early, facilitating early feedback on UI and request workflows
3. **Adaptability:** The project demands handling real change requests later in the semester, making rigid models like the traditional Waterfall model unsuitable

## 2. Individual Project Plan (Weeks 1 – 5)

| Week | Milestone / Goal | Deliverables | Status |
| :--- | :--- | :--- | :--- |
| **Week 1** | Problem Formulation | `week1/problem-statement.md` detailing problem definition and stakeholder analysis. | Completed |
| **Week 2** | Process cohesion & Planning | `week2/model-justification.md` with model selection and project schedule. | Completed |
| **Week 3** | Requirements Specification | `week3/srs-draft.md` containing functional and non-functional requirements
| **Week 4** | System Architecture & Use Case Modeling | `week4/use-cases-architecture.md` and initial UML diagrams. 
| **Week 5** | Prototype Design & Class/Sequence Diagrams | `week5/design-spec.md` with detailed UML class and sequence models Planned |
# Week 3: Software Requirements Specification (SRS) Draft

## 1. Introduction
### 1.1 Purpose
This document outlines the functional and non-functional requirements for the CampusFix prototype

### 1.2 Scope
CampusFix allows students and staff to submit maintenance requests, enables administrators to triage and assign work, and allows maintenance personnel to process requests to resolution

---

## 2. Functional Requirements (FR)

### 2.1 User Management & Authentication
* **FR-01:** System shall allow users (Students, Staff, Maintenance, Admin) to log in securely with their credentials.
* **FR-02:** System shall enforce role-based access control (RBAC).

### 2.2 Fault Reporting
* **FR-03:** Students/Staff shall be able to submit a new problem report specifying:
  * Location (Building, Room, Lab number)[span_36]
  * Fault Category (IT Equipment, Plumbing, Electrical, Furniture, Structural)
  * Description of the problem
  * Optional photo/attachment upload.
* **FR-04:** System shall assign a unique Tracking ID and record the submission timestamp for each report

### 2.3 Triage & Escalation
* **FR-05:** Triage staff shall be able to view all unassigned reports[span_40]
* **FR-06:** Triage staff shall be able to set problem priority (Low, Medium, High, Urgent)
* **FR-07:** Triage staff shall assign an open request to specific maintenance personnel

### 2.4 Maintenance & Status Management
* **FR-08:** Maintenance staff shall view their assigned tasks.
* **FR-09:** Maintenance staff shall update request status across its lifecycle (`Submitted` -> `Triaged` -> `In Progress` -> `Resolved` -> `Closed`)
* **FR-10:** System shall notify reporters automatically when status updates occur

### 2.5 Metrics & Reporting
* **FR-11:** System shall track response and resolution times for each request
* **FR-12:** System shall allow administrators to view metrics on unresolved issues and recurring faults

---

## 3. Non-Functional Requirements (NFR)

### 3.1 Performance & Usability
* **NFR-01 (Usability):** The reporting form shall be accessible and simple, requiring fewer than 4 steps to submit a report.
* **NFR-02 (Performance):** Status changes and page updates shall load within 2 seconds under normal campus load.

### 3.2 Security & Maintainability
* **NFR-03 (Security):** User data and tickets shall only be accessible to authorized roles.
* **NFR-04 (Maintainability):** The system architecture shall follow modular principles to allow easy integration of change requests and future updates
