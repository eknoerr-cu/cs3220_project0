# Wireframe Annotations

## Team Information
- Team name:
- Team members:
- Date:
- Wireframe tool used (HTML / Pencil / other):

---

## Purpose of This Document
This document explains how the wireframe maps to user requirements, data flow, and future implementation.
It should be readable without seeing the wireframe and should align directly with the Project 0 user stories and MVP backlog.

---

## Global Header
**Description:**  
Briefly describe the purpose of the global header and what information or actions it provides to the user.

**Elements included:**
- [ ] Application title
- [ ] Navigation links
- [ ] User information / status

**User stories supported:**
- US-__ :
- US-__ :

**Data shown or used:**
- Example: current user name, authentication status

**Backend required?**
- [ ] Yes
- [ ] No  
If yes, briefly explain (e.g., session/user API).

---

## Content Well 1 — Finder (Course Discovery)
**Purpose of this well:**  
(What problem does this well solve for the user?)

**UI elements included:**
- [ ] Search box
- [ ] Filters (department, credits, etc.)
- [ ] Course list / results

**User stories supported:**
- US-__ :
- US-__ :

**Inputs:**
- Example: search text, filter selections

**Outputs / displayed data:**
- Example: course code, title, credits, meeting time

**State ownership:**
- Is this well the source of truth for course data?
  - [ ] Yes
  - [ ] No

**Backend required?**
- [ ] Yes
- [ ] No  
If yes, list likely endpoints (e.g., `GET /courses`).

---

## Content Well 2 — Plan (4-year schedule)
**Purpose of this well:**

**UI elements included:**
- [ ] Selected course list
- [ ] Credit total
- [ ] Current semester
- [ ] Save / clear actions

**User stories supported:**
- US-__ :
- US-__ :

**Inputs:**
- Example: selected courses from Well 1

**Outputs / displayed data:**
- Example: planned courses, total credits, warnings

**State ownership:**
- Is this well the source of truth for the student’s plan?
  - [ ] Yes
  - [ ] No

**Backend required?**
- [ ] Yes
- [ ] No  
If yes, explain persistence needs (e.g., save plan to database).

---

## Content Well 3 — Requirements (Course Details / Inspector)
**Purpose of this well:**

**UI elements included:**
- [ ] Major / minor specific courses
- [ ] Electives / GenEds

**User stories supported:**
- US-__ :
- US-__ :

**Inputs:**
- Example: planned / taken courses from Well 2

**Outputs / displayed data:**
- Example: full major metadata

**Backend required?**
- [ ] Yes
- [ ] No  
If yes, list likely endpoints (e.g., `GET /courses/{id}`).

---

## Content Well 4 — Status (Alerts & Actions)
**Purpose of this well:**

**UI elements included:**
- [ ] Prerequisite warnings
- [ ] Missing requirements / credits hours

**User stories supported:**
- US-__ :
- US-__ :

**Triggers:**
- Example: adding a course with a missing prerequisite, exceeding credit limit

**Backend required?**
- [ ] Yes
- [ ] No  
If yes, explain briefly (e.g., rules engine, notification service).

---

## Cross-Well Interactions
Describe how data flows between wells.

- Which well triggers updates in other wells?
- What happens when a course is added or removed?
- Which actions require re-fetching data from the backend?

---

## Assumptions & Open Questions
List assumptions made during wireframing and any unresolved questions.

- Assumption 1:
- Assumption 2:
- Open question 1:

---

## Accessibility Notes (Brief)
List at least two accessibility considerations reflected in the wireframe.

- Example: keyboard navigation between wells
- Example: clear labeling of form controls

---

## Final Checklist
- [ ] All four content wells are clearly defined
- [ ] Each well maps to at least one user story
- [ ] Backend needs are identified
- [ ] Wireframe matches user stories
