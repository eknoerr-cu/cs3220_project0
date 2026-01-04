# Project 0 Wireframe Annotations

## Team Information
- Team name: Disciple Makers
- Team members: Peter, James, John
- Date: September 12, 2025
- Wireframe tool used: HTML (provided wireframe template)

---

## Purpose of This Document
This document explains how our wireframe supports the core requirements of the Student Planning application. It maps user stories to visual components, identifies data flow between functional areas, and outlines backend persistence needs that will guide implementation in later projects.

---

## Global Header
**Description:**  
The global header provides consistent navigation and user context across the application. It allows the user to move between major views and confirms authentication status.

**Elements included:**
- [x] Application title
- [x] Global navigation links
- [x] User status / login indicator

**User stories supported:**
- US-01: As a student, I want to see that I am logged in so I know my plan is saved.
- US-02: As a student, I want to navigate between planner views without losing my work.

**Data shown or used:**
- Current user name
- Authentication status

**Backend required?**
- [x] Yes  
User session data must be retrieved from the backend to determine login state.

---

## Content Well 1 — Course Discovery
**Purpose of this well:**  
Allows students to search and browse available courses before adding them to their plan.

**UI elements included:**
- [x] Search box
- [x] Filters (department, credits)
- [x] Course list / results

**User stories supported:**
- US-03: As a student, I want to search for courses by keyword.
- US-04: As a student, I want to filter courses by department and credit count.

**Inputs:**
- Search text
- Selected filters (department, credits)

**Outputs / displayed data:**
- Course code
- Course title
- Credit value
- Meeting days/times

**State ownership:**
- Is this well the source of truth for course data?
  - [ ] Yes
  - [x] No  
  Course data originates from the backend.

**Backend required?**
- [x] Yes  
Likely endpoints:
- `GET /courses`
- `GET /courses?department=CS&credits=3`

---

## Content Well 2 — My Plan / Schedule
**Purpose of this well:**  
Displays the student’s selected courses and summarizes their planned semester.

**UI elements included:**
- [x] Selected course list
- [x] Credit total
- [x] Conflict indicators
- [x] Save / clear actions

**User stories supported:**
- US-05: As a student, I want to add courses to my plan.
- US-06: As a student, I want to see my total credits.
- US-07: As a student, I want to be warned about time conflicts.

**Inputs:**
- Course selections from Content Well 1

**Outputs / displayed data:**
- Planned courses
- Total credit count
- Conflict warnings

**State ownership:**
- Is this well the source of truth for the student’s plan?
  - [x] Yes
  - [ ] No

**Backend required?**
- [x] Yes  
The plan must be persisted per user:
- `POST /plan`
- `GET /plan`
- `DELETE /plan`

---

## Content Well 3 — Course Details / Inspector
**Purpose of this well:**  
Provides in-depth information about a selected course to help the student make informed decisions.

**UI elements included:**
- [x] Course description
- [x] Instructor
- [x] Meeting times
- [x] Prerequisites

**User stories supported:**
- US-08: As a student, I want to view detailed course information.
- US-09: As a student, I want to see prerequisites before adding a course.

**Inputs:**
- Selected course ID from Content Well 1

**Outputs / displayed data:**
- Full course metadata
- Prerequisite list

**Backend required?**
- [x] Yes  
Likely endpoint:
- `GET /courses/{courseId}`

---

## Content Well 4 — Alerts & Actions
**Purpose of this well:**  
Centralizes system feedback and high-impact actions so the user can quickly respond to issues.

**UI elements included:**
- [x] Conflict warnings
- [x] Seat availability alerts
- [x] Registration or export actions

**User stories supported:**
- US-10: As a student, I want to be warned if my plan has conflicts.
- US-11: As a student, I want to export my plan.

**Triggers:**
- Adding overlapping courses
- Exceeding credit limits
- Low seat availability

**Backend required?**
- [x] Yes  
Backend logic is needed to evaluate rules and generate alerts.

---

## Cross-Well Interactions
- Selecting a course in Well 1 updates Well 3.
- Adding a course in Well 1 updates Well 2.
- Conflicts detected in Well 2 generate alerts in Well 4.
- Saving the plan in Well 2 updates backend state and header login context.

---

## Assumptions & Open Questions
**Assumptions:**
- Course data is relatively static during the semester.
- Students can only plan one semester at a time.

**Open Questions:**
- Should prerequisite enforcement be strict or advisory?
- Will registration actions actually enroll the student or only export data?

---

## Mapping to MVP Backlog
**Must-have features represented:**
- Course search and filtering
- Add/remove courses
- Credit totals and conflict warnings
- Save and load plan

**Deferred features:**
- Degree audit integration
- Advisor approval workflow

---

## Accessibility Notes (Brief)
- All interactive elements are reachable via keyboard navigation.
- Form controls include visible labels and sufficient spacing.

---

## Final Checklist
- [x] All four content wells are clearly defined
- [x] Each well maps to at least one user story
- [x] Backend needs are identified
- [x] Wireframe matches user stories and MVP backlog
