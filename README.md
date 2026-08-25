# Lab 1 – Requirements Engineering & UML Use-Case Modelling

## Alumni Mentorship & Mock Interview Platform

**PES University – Dept. of CSE**  
**Problem Statement #06 – Campus & Academic Operations**

## 1. Objective

This lab converts the given Alumni Mentorship & Mock Interview Platform scenario into clear, testable Functional Requirements (FRs), Non-Functional Requirements (NFRs), a UML Use-Case Diagram, and one detailed Use-Case Flow.

The scenario focuses on connecting students with alumni working in specialized domains through intelligent mentor matching, calendar-based booking, and structured post-interview scorecard recording.

## 2. Actors

| Actor | Role |
|---|---|
| **Student Mentee** | Searches for suitable alumni mentors, views mentor information, books mentorship/mock-interview sessions, and views feedback. |
| **Alumni Mentor** | Provides mentorship, manages availability, conducts mock interviews, and records feedback/scorecards. |
| **Calendar & Meeting Service** | External service used by the platform to create calendar events and provide meeting links. |

> The first two actors are the target stakeholders specified in the problem statement. The Calendar & Meeting Service is an external supporting actor inferred directly from the scenario's calendar-booking and meeting-link requirements.

## 3. Requirements

The lab requires exactly five Functional Requirements and two Non-Functional Requirements. FR-001 and NFR-001 follow the instructor-provided scenario guidelines; the remaining requirements are derived from the same scenario.

### Functional Requirements

- **FR-001 – Intelligent Mentor Matching**
- **FR-002 – Mentor Profile and Availability Viewing**
- **FR-003 – Mentorship Session Booking**
- **FR-004 – Mock Interview Booking**
- **FR-005 – Post-Session Feedback and Scorecard Recording**

### Non-Functional Requirements

- **NFR-001 – Performance & Security**
- **NFR-002 – Availability and Reliability**

See [`Requirements/Requirements_Table.md`](Requirements/Requirements_Table.md) for the complete SRS-style table.

## 4. UML Use-Case Model

### Main use cases

**Student Mentee**
- Find / Match Mentor
- View Mentor Profile & Availability
- Book Mentorship Session
- Book Mock Interview
- View Feedback & Scorecard
- Reschedule Booked Session

**Alumni Mentor**
- Manage Profile
- Manage Availability
- Conduct Mentorship Session
- Conduct Mock Interview
- Record Feedback & Scorecard

**Calendar & Meeting Service**
- Create Calendar Event
- Generate Meeting Link

### UML relationships

- `<<include>>` is used for behavior that is always required.
  - **Book Mentorship Session** includes **Check Availability**.
  - **Book Mentorship Session** includes **Create Calendar Event**.
  - **Book Mentorship Session** includes **Generate Meeting Link**.
  - **Book Mock Interview** includes **Check Availability**, **Create Calendar Event**, and **Generate Meeting Link**.
  - **Conduct Mock Interview** includes **Record Feedback & Scorecard**.

- `<<extend>>` is used for optional/conditional behavior.
  - **Reschedule Booked Session** extends **Book Mentorship Session** because rescheduling is an optional action after a session has been booked.

The editable PlantUML source is in [`UML/Use_Case_Diagram.puml`](UML/Use_Case_Diagram.puml).

## 5. Selected Use-Case Flow

**UC-03 – Book Mentorship Session**

The detailed flow includes:
- Preconditions
- Postconditions
- Main Success Scenario
- Alternate Flow

See [`Use_Case_Flow/Book_Mentorship_Session.md`](Use_Case_Flow/Book_Mentorship_Session.md).

## 6. Repository Structure

```text
Alumni-Mentorship-Mock-Interview-Lab1/
│
├── README.md
│
├── Requirements/
│   └── Requirements_Table.md
│
├── UML/
│   └── Use_Case_Diagram.puml
│
└── Use_Case_Flow/
    └── Book_Mentorship_Session.md
```

## 7. Lab Checklist

- [x] Exactly 5 Functional Requirements
- [x] Exactly 2 Non-Functional Requirements
- [x] Req ID included
- [x] Type included
- [x] Every requirement uses a clear “The system shall…” statement
- [x] Priority included
- [x] Measurable pass/fail acceptance criteria included
- [x] Rationale included
- [x] Comments included
- [x] At least 3 actors
- [x] At least 5 use cases
- [x] `<<include>>` relationship included
- [x] `<<extend>>` relationship included
- [x] Main Success Scenario included
- [x] At least one Alternate Flow included

## 8. Tools

- Draw.io / diagrams.net or Lucidchart for the UML diagram
- PlantUML source included for reproducible diagram generation
- GitHub for submission
- Word/PDF for the Use-Case Flow document
