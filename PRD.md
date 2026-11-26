# Quadrant: Campus Navigation System
## Product Requirements Document (PRD)

| | |
|---|---|
| **Course** | BU-COS-209 |
| **Product** | Quadrant |
| **Document type** | Product Requirements Document |
| **Version** | 1.0 |
| **Date** | 25 November 2026 |
| **Team members** | Uzoma David Chisom (25/0970) ,Osowe marvelous Ayodele (25/1127) ,Osindero Iyanulolu Samuel (25/1602) ,Omeka Divine Ekenechuckwu (25/2322) |
| **Status** | Final draft for submission |

---

## Table of Contents

1. [Executive Summary](#1-executive-summary)
2. [Problem Statement](#2-problem-statement)
3. [Vision, Goals and Non-Goals](#3-vision-goals-and-non-goals)
4. [Research Methodology](#4-research-methodology)
5. [Survey Results](#5-survey-results)
6. [Interview Findings](#6-interview-findings)
7. [Key Insights and Design Implications](#7-key-insights-and-design-implications)
8. [User Personas](#8-user-personas)
9. [Competitive Analysis](#9-competitive-analysis)
10. [Proposed Solution](#10-proposed-solution)
11. [User Stories](#11-user-stories)
12. [Functional Requirements](#12-functional-requirements)
13. [Non-Functional Requirements](#13-non-functional-requirements)
14. [MVP Definition](#14-mvp-definition)
15. [Roadmap and Release Plan](#15-roadmap-and-release-plan)
16. [User Flows](#16-user-flows)
17. [System Architecture](#17-system-architecture)
18. [Data Model](#18-data-model)
19. [Success Metrics](#19-success-metrics)
20. [Risks and Mitigations](#20-risks-and-mitigations)
21. [Assumptions, Constraints and Dependencies](#21-assumptions-constraints-and-dependencies)
22. [Team Roles and Timeline](#22-team-roles-and-timeline)
23. [Open Questions](#23-open-questions)
24. [Appendix](#24-appendix)

---

## 1. Executive Summary

**Quadrant** is a campus navigation system that helps students, staff and visitors find their way around campus quickly and confidently. It combines an outdoor campus map, indoor building and room guidance, accessible route planning, and class-schedule-aware directions in one simple experience.

Our research found that navigating campus is a frequent source of stress and lost time, especially for first-year students and people with mobility needs. General-purpose map apps handle roads well but do not understand campus buildings, room numbering, internal corridors, shortcuts or accessible entrances.

Quadrant's MVP focuses on the highest-value needs identified in research:

1. Search for any building, room or facility.
2. Get step-by-step walking directions across campus, including accessible routes.
3. Get indoor guidance to a specific room or floor.
4. Use the app with a weak or no connection (offline basic map).
5. See "next class" directions based on a timetable the user enters.

The platform and programming language have not yet been chosen. Section 17 defines the architecture in a language-agnostic way and lists the criteria for the team's technology decision.

---

## 2. Problem Statement

### 2.1 Problem

Students, staff and visitors waste time and experience stress finding buildings, rooms and facilities on campus. Existing tools do not model the campus accurately, particularly the indoors.

### 2.2 Who is affected

| Group | How they are affected |
|---|---|
| New students | Unfamiliar with building names, room codes and the campus layout; late to early classes and orientation events |
| Continuing students | Struggle with rarely used buildings, exam venues and temporary event locations |
| Students with mobility needs | Cannot easily find step-free routes, working lifts or accessible entrances |
| Staff and lecturers | Lose time giving directions; arrive late between sessions across campus |
| Visitors, applicants, guests | No reliable way to find reception, offices or event venues |

### 2.3 Why it matters

- Late arrival disrupts classes and affects performance and confidence.
- Asking for directions repeatedly increases anxiety for new students.
- Inaccessible route planning is an equity problem, not just a convenience problem.
- Staff and security time is spent on repetitive wayfinding questions.

### 2.4 Problem statement (summary)

> *How might we help every person on campus reach any destination, indoors or outdoors, quickly, accessibly and without needing to ask for help?*

---

## 3. Vision, Goals and Non-Goals

### 3.1 Vision

Everyone on campus can get from where they are to where they need to be, with confidence, in under a minute of planning.

### 3.2 Product goals

| # | Goal | Measure |
|---|---|---|
| G1 | Reduce time spent finding destinations | Median time from opening app to starting a route under 30 seconds |
| G2 | Reduce navigation-related lateness | At least 30% fewer self-reported late arrivals among active users |
| G3 | Make campus accessible to plan | Accessible route option available for 100% of mapped destinations |
| G4 | Achieve adoption | 40% of enrolled students try the app in the first semester |
| G5 | Keep it reliable | Route and search accuracy of at least 95% on mapped locations |

### 3.3 Non-goals (for MVP)

- Turn-by-turn navigation off campus or between cities.
- Real-time indoor positioning using hardware beacons.
- Payments, ticketing or food ordering.
- A full timetable management system (Quadrant only reads a simple user-entered schedule).
- Social features such as chat or friend tracking.
- Augmented reality navigation.

---

## 4. Research Methodology

The team ran two complementary research activities to understand the problem and validate the solution direction.

| Method | Purpose | Sample | Format |
|---|---|---|---|
| **Online survey** | Quantify the size and shape of the problem; prioritise features | 60 respondents | 14 questions, about 4 minutes |
| **Semi-structured interviews** | Understand context, behaviours, frustrations and unmet needs in depth | 8 participants | About 20 minutes each |

### 4.1 Sampling

- **Survey (n = 60):** students from different year levels; sampled by sharing a link in class group chats and student communities.
- **Interviews (n = 8):** purposive sample to cover a range of experience levels and needs, including one student with a mobility impairment and one member of staff.

### 4.2 Limitations

- Convenience sampling; results may skew toward people active in group chats.
- Self-reported behaviour may differ from actual behaviour.
- Small sample sizes; findings are directional, not statistically conclusive.
- **All responses in this document are simulated** (see disclosure at the top).

### 4.3 Survey respondent profile

| Year of study | Respondents | Share |
|---|---|---|
| Year 1 | 27 | 45% |
| Year 2 | 15 | 25% |
| Year 3 | 11 | 18% |
| Year 4 | 7 | 12% |
| **Total** | **60** | **100%** |

---

## 5. Survey Results

### 5.1 Have you ever been lost or struggled to find a place on campus?

| Response | Count | Share |
|---|---|---|
| Yes | 47 | 78% |
| No | 13 | 22% |

### 5.2 How often per semester have you been late because you could not find a venue?

| Frequency | Count | Share |
|---|---|---|
| Never | 8 | 13% |
| 1 to 2 times | 17 | 28% |
| 3 to 5 times | 20 | 33% |
| 6 or more times | 15 | 25% |

**Finding:** 87% of respondents reported at least one late arrival due to navigation; 58% reported three or more.

### 5.3 What do you currently use to find places? (multi-select)

| Method | Count | Share of respondents |
|---|---|---|
| Google Maps (or similar) | 41 | 68% |
| Asking other students or staff | 33 | 55% |
| Campus website map | 19 | 32% |
| Printed or PDF map | 12 | 20% |
| Nothing / just wander | 4 | 7% |

### 5.4 How satisfied are you with current tools for finding rooms inside buildings? (1 = very unsatisfied, 5 = very satisfied)

| Rating | Count |
|---|---|
| 1 | 19 |
| 2 | 21 |
| 3 | 12 |
| 4 | 6 |
| 5 | 2 |
| **Average** | **2.2** |

### 5.5 Feature importance (average rating, 1 = not important, 5 = essential)

| Feature | Average | Rank |
|---|---|---|
| Indoor navigation to a specific room | 4.6 | 1 |
| Search by room or building name/code | 4.5 | 2 |
| Accessible (step-free) routes | 4.2 | 3 |
| Directions to next class from my timetable | 4.1 | 4 |
| Works offline / low data | 3.9 | 5 |
| Shuttle or transport times | 3.8 | 6 |
| Live event locations | 3.4 | 7 |
| Crowd or occupancy indicators | 3.3 | 8 |

### 5.6 Preferred platform

| Platform | Count | Share |
|---|---|---|
| Mobile app (iOS/Android) | 32 | 53% |
| Web app in the phone browser | 22 | 37% |
| No preference | 6 | 10% |

### 5.7 Likelihood to use a dedicated campus navigation app

| Response | Count | Share |
|---|---|---|
| Very likely | 29 | 48% |
| Likely | 22 | 37% |
| Neutral | 6 | 10% |
| Unlikely | 3 | 5% |
| Very unlikely | 0 | 0% |

**Finding:** 85% are likely or very likely to use Quadrant.

### 5.8 Selected open-ended survey comments (simulated)

- "Google Maps takes me to the building's front gate, then I'm on my own."
- "Room codes make no sense unless you already know the system."
- "Please show which entrance is closest to my lecture hall."
- "Exam venues are the worst, I once went to the wrong block."
- "Make it work without data. My bundle runs out quickly."

---

## 6. Interview Findings

### 6.1 Participants

| ID | Profile | Year / Role |
|---|---|---|
| P1 | Student | Year 1 |
| P2 | Student | Year 1 |
| P3 | Student | Year 1 |
| P4 | Student | Year 2 |
| P5 | Student | Year 3 |
| P6 | Student | Year 4 |
| P7 | Student with a mobility impairment (wheelchair user) | Year 2 |
| P8 | Lecturer | Staff |

### 6.2 Themes

**Theme 1: The first weeks are the hardest.**
P1, P2 and P3 described feeling embarrassed asking for directions repeatedly. P2 said they arrived late to two lectures in the first week.
> P2: "I left early and still got to the wrong building. Then I couldn't find the right floor."

**Theme 2: Outdoor maps work, indoor guidance does not.**
P4 and P5 use Google Maps to reach buildings but then rely on guesswork inside.
> P5: "Block B has wings that don't connect on every floor. No app tells you that."

**Theme 3: Room codes are confusing.**
All six non-staff student participants said they did not understand the room code format when they started.

**Theme 4: Accessibility is an afterthought.**
P7 plans routes the day before and often finds an entrance or lift out of service.
> P7: "I need to know which entrance has a ramp, and whether the lift is working, before I leave my room."

**Theme 5: Schedules drive urgency.**
P4 and P6 said they mostly need directions "to my next class", not general exploration. They would value a one-tap route.

**Theme 6: Connectivity is unreliable.**
P3, P5 and P6 mentioned limited data and weak signal inside certain buildings.

**Theme 7: Staff and visitors also need help.**
P8 gets asked for directions by visitors and new students several times per week and is sometimes late to sessions at distant venues.

### 6.3 Pain point frequency across interviews

| Pain point | Participants mentioning it |
|---|---|
| Cannot find a room inside a building | 7 of 8 |
| Confusing room code system | 6 of 8 |
| Late to class due to navigation | 6 of 8 |
| Needs offline or low-data use | 3 of 8 |
| Accessible route unknown or unreliable | 2 of 8 (critical severity for P7) |
| Embarrassment about asking for help | 4 of 8 |

### 6.4 Feature reactions to concept prototype (paper sketches)

| Concept | Reaction |
|---|---|
| Search bar with room code autocomplete | Strongly positive (8 of 8) |
| "Navigate to next class" button | Strongly positive (6 of 8) |
| Floor-by-floor indoor route steps with photos of landmarks | Positive (7 of 8) |
| Accessible route toggle with lift status | Critical for P7; positive for 5 others |
| Crowd indicators | Mixed; seen as nice to have |

---

## 7. Key Insights and Design Implications

| # | Insight | Design implication |
|---|---|---|
| 1 | Most people already reach the correct building but fail indoors | Prioritise indoor wayfinding in the MVP, not just outdoor routing |
| 2 | Room codes are a barrier | Accept natural search ("Lab 3 Engineering") and decode codes in the UI (building, floor, room) |
| 3 | Accessibility needs are severe for a minority and useful for many | Build an accessible-route mode from the start; include lift and ramp data |
| 4 | Most trips are to the next class | Make schedule-based "go to next class" a one-tap feature |
| 5 | Data and signal are constrained | Cache the campus map and graph on the device; support offline routing |
| 6 | First-years are the largest and most motivated group | Include a lightweight first-launch tour and a "Popular places" list |
| 7 | Landmarks help more than distances | Describe steps with landmarks ("Turn left at the main stairs") |

---

## 8. User Personas

### Persona 1: Amara, the First-Year Student
- **Age:** 18 | **Goal:** Get to every class on time in her first month
- **Behaviour:** Leaves early, checks her phone constantly, hesitates to ask for help
- **Frustrations:** Room codes, identical-looking buildings, running out of mobile data
- **Needs:** Simple search, clear indoor steps, offline use, "next class" button
- **Quote:** *"I just want to know which door to walk through."*

### Persona 2: Tobi, the Final-Year Student
- **Age:** 22 | **Goal:** Move efficiently between lectures, library and lab
- **Behaviour:** Knows the main routes, but is caught out by exam venues and events
- **Frustrations:** Last-minute venue changes, unfamiliar blocks
- **Needs:** Fast search, shortcuts, event and exam venue pins

### Persona 3: Daniel, the Student Who Uses a Wheelchair
- **Age:** 20 | **Goal:** Travel between buildings independently and predictably
- **Behaviour:** Plans routes the evening before; checks for ramps and lifts
- **Frustrations:** Out-of-service lifts, unmarked step-free entrances, long detours
- **Needs:** Accessible-only routing, lift/ramp status, estimated travel time that reflects his pace
- **Quote:** *"A wrong turn costs me ten minutes, not ten seconds."*

### Persona 4: Dr. Mensah, the Lecturer
- **Age:** 45 | **Goal:** Arrive at sessions on time, help visitors find offices
- **Behaviour:** Walks between distant venues; frequently asked for directions
- **Frustrations:** Repeating directions, tight transitions between sessions
- **Needs:** Quick search for a venue, shareable location links

### Persona 5: Visitor, the Prospective Student's Parent
- **Goal:** Find admissions office and event hall on open day
- **Needs:** Zero-setup access (no account), clear signage-like instructions

---

## 9. Competitive Analysis

| Capability | Google Maps | Campus website PDF map | Printed map | Generic indoor apps | **Quadrant (target)** |
|---|---|---|---|---|---|
| Outdoor campus walking routes | Yes | No | Static | Limited | **Yes** |
| Building entrances | Partial | Partial | Partial | Rare | **Yes** |
| Indoor room-level guidance | Rarely | No | No | Yes, but paid and needs hardware | **Yes (map-based)** |
| Room code understanding | No | No | No | Limited | **Yes** |
| Accessible route with lift status | Limited | No | No | Limited | **Yes** |
| Offline use | Partial | Yes (static) | Yes | Varies | **Yes** |
| Schedule-aware directions | No | No | No | No | **Yes** |
| Campus-specific updates | No | Slow | No | Slow | **Yes (admin tool)** |

**Positioning:** Quadrant is the only option that combines campus-specific indoor wayfinding, accessibility and schedule awareness, without expensive hardware.

---

## 10. Proposed Solution

### 10.1 Solution overview

Quadrant is a navigation experience built on a **campus graph**: a structured map of buildings, entrances, corridors, stairs, lifts, ramps and rooms. A routing engine computes paths over this graph using user preferences (fastest or accessible) and presents them as simple, landmark-based steps on a map.

### 10.2 Core capabilities

1. **Smart search:** find buildings, rooms, offices, labs, lecture halls, toilets, cafeterias, print centres and more; understands room codes and common nicknames.
2. **Campus routing:** walking directions between any two points, with estimated times.
3. **Indoor guidance:** multi-floor steps ("Enter by the north door, take the lift to Floor 2, turn right").
4. **Accessible mode:** step-free routes only; shows lift and ramp status.
5. **Next-class navigation:** the user enters their timetable; Quadrant offers one-tap directions and a "leave by" time.
6. **Offline mode:** download the campus map and routing data once.
7. **Admin tool:** staff can update locations, room labels and lift status.

### 10.3 Design principles

- **Simple first:** one search bar, one primary action.
- **Landmark-led:** describe routes the way people talk.
- **Inclusive by default:** accessibility is core, not an add-on.
- **Works anywhere:** low data, weak signal, older phones.
- **Private:** no account needed for core use; location stays on the device.

---

## 11. User Stories

### Search and discovery
- **US-01:** As a new student, I want to search for a room by code or name so that I can find it without asking anyone.
- **US-02:** As a visitor, I want to find the admissions office without creating an account.
- **US-03:** As a student, I want to browse categories (lecture halls, labs, toilets, food) so that I can discover facilities nearby.

### Navigation
- **US-04:** As a student, I want walking directions from my current location to a building so that I arrive on time.
- **US-05:** As a student, I want indoor steps to a specific room so that I do not get lost inside the building.
- **US-06:** As a wheelchair user, I want step-free routes only so that I can travel independently.
- **US-07:** As a wheelchair user, I want to see whether a lift is working before I plan my route.

### Schedule
- **US-08:** As a student, I want to add my classes so that I can tap "Go to next class".
- **US-09:** As a student, I want a "leave by" reminder so that I am not late.

### Offline and sharing
- **US-10:** As a student with limited data, I want to download the campus map so that I can navigate offline.
- **US-11:** As a lecturer, I want to share a location link so that visitors can find me.

### Administration
- **US-12:** As a campus facilities administrator, I want to update room labels and lift status so that information stays accurate.

---

## 12. Functional Requirements

Priority uses MoSCoW: **M** = Must, **S** = Should, **C** = Could, **W** = Won't (this release).

### 12.1 Search

| ID | Requirement | Priority |
|---|---|---|
| FR-S1 | Search across buildings, rooms, facilities and offices with autocomplete | M |
| FR-S2 | Understand room code formats (e.g., building + floor + room) | M |
| FR-S3 | Support nicknames and aliases (e.g., "Main Hall") | S |
| FR-S4 | Show recent searches and popular places | S |
| FR-S5 | Filter by category | S |
| FR-S6 | Tolerate typos (fuzzy search) | S |

### 12.2 Map and routing

| ID | Requirement | Priority |
|---|---|---|
| FR-R1 | Interactive campus map with buildings labelled | M |
| FR-R2 | Show user's current location on the map (with permission) | M |
| FR-R3 | Compute shortest walking route between any two mapped points | M |
| FR-R4 | Accessible route option (step-free only) | M |
| FR-R5 | Display estimated walking time and distance | M |
| FR-R6 | Indoor route steps across floors with landmarks | M |
| FR-R7 | Floor selector for multi-storey buildings | M |
| FR-R8 | Re-route if the user leaves the path | S |
| FR-R9 | Choose a start point manually if GPS is unavailable | M |
| FR-R10 | Avoid closed paths or out-of-service lifts | S |

### 12.3 Schedule

| ID | Requirement | Priority |
|---|---|---|
| FR-T1 | Add, edit and delete classes (course, day, time, room) | M |
| FR-T2 | "Go to next class" one-tap route | M |
| FR-T3 | "Leave by" time suggestion and optional notification | S |
| FR-T4 | Import schedule from a file (e.g., calendar export) | C |

### 12.4 Offline

| ID | Requirement | Priority |
|---|---|---|
| FR-O1 | Download campus map and routing data for offline use | M |
| FR-O2 | Search and routing work without a connection | M |
| FR-O3 | Prompt for data updates when connected | S |

### 12.5 Accessibility and inclusion

| ID | Requirement | Priority |
|---|---|---|
| FR-A1 | Show ramps, lifts and accessible entrances on the map | M |
| FR-A2 | Show lift status (working / out of service) | S |
| FR-A3 | Screen-reader support and sufficient colour contrast | M |
| FR-A4 | Adjustable text size | S |
| FR-A5 | Voice-readable step instructions | C |

### 12.6 Sharing and help

| ID | Requirement | Priority |
|---|---|---|
| FR-H1 | Share a location or route via link | S |
| FR-H2 | First-launch tutorial | S |
| FR-H3 | Report incorrect or blocked location | S |

### 12.7 Administration

| ID | Requirement | Priority |
|---|---|---|
| FR-AD1 | Secure admin login | M |
| FR-AD2 | Add/edit/remove locations, aliases and categories | M |
| FR-AD3 | Update lift and path status | S |
| FR-AD4 | Review user-submitted reports | C |

### 12.8 Explicitly out of scope for this release

| ID | Requirement | Priority |
|---|---|---|
| FR-X1 | Live indoor positioning with beacons | W |
| FR-X2 | Augmented reality guidance | W |
| FR-X3 | Crowd and occupancy heat maps | W |
| FR-X4 | Social and friend-location features | W |

---

## 13. Non-Functional Requirements

| Category | Requirement |
|---|---|
| **Performance** | Search results in under 300 ms; route computed in under 1 second for any pair of campus points |
| **Availability** | 99% uptime for online services; core features available offline |
| **Reliability** | Offline data must remain valid and not corrupt after an interrupted download |
| **Usability** | A first-time user can complete a search and start a route in under 30 seconds without instructions |
| **Accessibility** | Meets WCAG 2.1 AA for contrast, labels and navigation |
| **Compatibility** | Works on phones from the last 5 years; low-end devices supported |
| **Data usage** | Initial offline pack under 50 MB; routine usage under 2 MB per day |
| **Privacy** | Core use requires no account; location is processed on the device and not stored on servers; comply with applicable data protection law |
| **Security** | Admin access protected by authentication and role-based permissions; encrypted transport |
| **Maintainability** | Campus data can be updated without releasing a new app version |
| **Scalability** | Supports the full campus population with concurrent peak usage at class changeovers |
| **Localisation** | English at launch; structure supports adding languages |

---

## 14. MVP Definition

### 14.1 MVP principle

Deliver the smallest product that lets a first-year student find and reach any class on campus, with an accessible-route option, even without data.

### 14.2 In scope for MVP

| Area | MVP features |
|---|---|
| Search | Building and room search with room-code decoding, autocomplete, categories |
| Map | Campus map, current location, floor selector |
| Routing | Shortest route, accessible route, indoor steps with landmarks |
| Schedule | Manual timetable entry, "Go to next class" |
| Offline | Downloadable map and routing data |
| Accessibility | Ramps and lifts displayed, screen-reader labels, high contrast |
| Admin | Simple admin tool to edit locations and lift status |

### 14.3 Not in MVP (later releases)

Schedule import, leave-by notifications, route sharing, user reports, voice guidance, event pins, shuttle times, multilingual support.

### 14.4 MVP coverage

To be useful, the MVP will map the following first:

1. All main teaching buildings and their entrances.
2. All lecture halls, labs and exam venues.
3. Library, administration, student services and main cafeterias.
4. All lifts, ramps and step-free entrances.

### 14.5 MVP acceptance criteria

| # | Criterion |
|---|---|
| AC1 | A user can search for any mapped room and get a route in under 30 seconds |
| AC2 | Accessible mode never returns a route that includes stairs |
| AC3 | Search and routing work in airplane mode after the offline pack is downloaded |
| AC4 | "Go to next class" opens the correct route for a saved timetable entry |
| AC5 | Admin can change a room label or lift status and users see it after the next sync |
| AC6 | Passes usability test: at least 4 of 5 new users complete the core task unaided |

### 14.6 MVP validation plan

- Run a usability test with 5 first-year students on 3 tasks (find a room, accessible route, offline use).
- Measure task success, time on task and satisfaction (SUS score target of 75 or above).
- Fix top issues before wider release.

---

## 15. Roadmap and Release Plan

| Phase | Focus | Key deliverables |
|---|---|---|
| **Phase 0: Discovery** (complete) | Research and requirements | Survey, interviews, PRD |
| **Phase 1: Foundation** | Data and architecture | Campus map data collection, graph model, technology decision |
| **Phase 2: MVP build** | Core product | Search, routing, indoor steps, accessible mode, offline pack |
| **Phase 3: MVP test** | Validation | Usability testing, accessibility review, bug fixing |
| **Phase 4: Release 1.0** | Launch to students | Orientation-week rollout, help tour, admin training |
| **Phase 5: Release 1.1** | Convenience | Leave-by reminders, route sharing, schedule import |
| **Phase 6: Release 2.0** | Expansion | Events, shuttle times, multilingual, user reports, analytics dashboard |

---

## 16. User Flows

### 16.1 Find and navigate to a room

```
Open app
  -> Search bar: type "ENG 2.14"
  -> Select result (Engineering Block, Floor 2, Room 14)
  -> Choose route type (Fastest / Accessible)
  -> View route overview (time, distance)
  -> Start navigation
  -> Outdoor steps -> Enter building -> Indoor steps (stairs/lift) -> Arrive
```

### 16.2 Go to next class

```
Open app -> Tap "Next class" card -> Route preview -> Start
```

### 16.3 First-time setup

```
Launch -> Short tutorial (3 screens) -> Allow location (optional)
       -> Offer to download offline pack -> Home screen
```

### 16.4 Admin update

```
Admin login -> Select location -> Edit label or status -> Save -> Published to users on next sync
```

---

## 17. System Architecture

The programming language and platform are **not yet chosen**. This section describes a language-agnostic architecture and the criteria for the decision.

### 17.1 Logical components

```
+-------------------+      +----------------------+      +--------------------+
|  Client app       | <--> |  Campus API          | <--> |  Campus database   |
|  (UI, map, local  |      |  (search, routing    |      |  (locations, graph |
|  cache, offline)  |      |  data, sync, admin)  |      |  schedule optional)|
+-------------------+      +----------------------+      +--------------------+
         ^                            ^
         |                            |
  Local storage                 Admin web tool
  (offline pack,                (edit locations,
  user timetable)               lift status)
```

| Component | Responsibility |
|---|---|
| **Client app** | Map display, search UI, route display, timetable, offline storage, local routing |
| **Routing engine** | Shortest-path search over the campus graph with an accessibility filter; runs on the client for offline use |
| **Campus API** | Serves campus data and updates; handles sync and admin changes |
| **Campus database** | Stores locations, graph nodes/edges, categories, aliases, status |
| **Admin tool** | Authenticated interface for staff to maintain data |

### 17.2 Key design decisions

1. **Routing runs on the device** using a downloaded graph, enabling offline use and removing the need to send user location to servers.
2. **Campus data is versioned**; the app checks for new versions when online.
3. **Accessibility is a property of graph edges** (e.g., stairs vs. ramp), so routing can exclude unsuitable edges.
4. **Indoor guidance is graph-based**, not sensor-based, to avoid hardware cost.

### 17.3 Technology decision criteria

| Criterion | Why it matters |
|---|---|
| Team familiarity | Four-person team with limited time |
| Cross-platform reach | Survey showed mixed preference between app and web |
| Offline support | Core requirement |
| Mapping library support | Needed for custom indoor maps |
| Learning curve and delivery speed | Deadline-driven |
| Cost | Student project budget |

**Decision status:** open (see Section 23). The team will compare at least two options against these criteria and record the outcome in a short decision log.

---

## 18. Data Model

### 18.1 Main entities

| Entity | Key fields |
|---|---|
| **Building** | id, name, aliases, code, coordinates, entrances |
| **Floor** | id, building_id, level, label |
| **Location (Room/POI)** | id, floor_id, name, code, category, aliases, node_id |
| **Node** | id, coordinates, floor_id, type (corridor, door, stairs, lift, ramp, outdoor) |
| **Edge** | id, from_node, to_node, distance, accessible (true/false), status (open/closed) |
| **Category** | id, name (lecture hall, lab, toilet, food, etc.) |
| **Lift/Ramp status** | id, node_id, state, last_updated |
| **Class entry (local)** | id, course, day, start, end, location_id |
| **Data version** | version, published_at |

### 18.2 Relationships

- A **Building** has many **Floors**; a **Floor** has many **Locations**.
- **Nodes** are connected by **Edges** to form the walkable campus graph.
- Each **Location** links to one **Node** (its door or entrance).
- **Class entries** reference a **Location** and are stored only on the user's device.

---

## 19. Success Metrics

| Metric | Definition | Target (first semester) |
|---|---|---|
| Adoption | Share of enrolled students who open the app at least once | 40% |
| Activation | Users who complete a route in their first session | 60% |
| Retention | Users active in week 4 after install | 35% |
| Task time | Median time from open to route start | Under 30 s |
| Search success | Searches that lead to a selected result | 90% |
| Lateness | Self-reported navigation-related lateness among active users | 30% reduction |
| Accessibility use | Routes completed using accessible mode | Tracked; zero stair errors |
| Satisfaction | In-app rating or SUS score | 4.2 of 5 or SUS 75 |
| Data freshness | Time to publish a reported error | Under 48 hours |

Metrics will be collected in an anonymous, privacy-preserving way.

---

## 20. Risks and Mitigations

| # | Risk | Likelihood | Impact | Mitigation |
|---|---|---|---|---|
| R1 | Incomplete or inaccurate campus data | High | High | Prioritise mapping core buildings; field-walk and verify; admin tool and report feature |
| R2 | Indoor layouts differ from floor plans | Medium | High | Verify on-site; collect landmark photos |
| R3 | Team lacks skills in the chosen technology | Medium | High | Choose by familiarity; time-box a prototype spike |
| R4 | Time limit for the project | High | High | Strict MVP scope; Must-haves first |
| R5 | GPS is poor near buildings | High | Medium | Manual start-point selection; entrance-based routing |
| R6 | Lift status becomes stale | Medium | Medium | Show "last updated"; clear admin ownership |
| R7 | Low adoption | Medium | Medium | Orientation-week promotion; no sign-up required |
| R8 | Privacy concerns about location | Low | High | Process location on-device; no tracking; clear privacy note |
| R9 | Campus changes (construction, closures) | Medium | Medium | Edge status and admin updates |
| R10 | Accessibility errors cause real harm or frustration | Low | High | Test accessible routes with a real user; conservative defaults |

---

## 21. Assumptions, Constraints and Dependencies

### Assumptions
- Most users have a smartphone with a modern browser or can install an app.
- Floor plans or permission to survey buildings are available.
- The university permits mapping of campus buildings.

### Constraints
- Four-person team, fixed academic deadline.
- No programming language or platform chosen yet.
- Zero or minimal budget; free or open-source tools preferred.
- No indoor positioning hardware.

### Dependencies
- Access to building floor plans or site surveys.
- A map data source or base map suitable for custom editing.
- Facilities team input for lift and ramp information.

---

## 22. Team Roles and Timeline

### 22.1 Proposed roles (4 members)

| Role | Responsibilities |
|---|---|
| **Team leader / Product owner** | Scope, priorities, coordination, final submission |
| **Research and UX lead** | Surveys, interviews, user flows, usability tests |
| **Technical lead** | Architecture, technology decision, routing logic |
| **Data and QA lead** | Campus data collection, testing, accessibility checks |

All members contribute to documentation and review.

### 22.2 Submission process

- The completed `PRD.md` is pushed to the team's GitHub branch **once, by a single designated team member**, to keep the history clean.
- All other members send changes to that person before the push.

### 22.3 Indicative timeline

| Week | Milestone |
|---|---|
| 1 | Research, problem definition, PRD submitted |
| 2 | Technology decision, campus data plan, prototype of search and map |
| 3 to 4 | Routing, indoor steps, accessible mode |
| 5 | Offline pack, timetable and "next class" |
| 6 | Usability testing, fixes, final demo |

---

## 23. Open Questions

| # | Question | Owner | Needed by |
|---|---|---|---|
| Q1 | Which platform and programming language will we use? | Technical lead | Start of Phase 1 |
| Q2 | Can we obtain official floor plans, or must we survey manually? | Data and QA lead | Week 2 |
| Q3 | Which base map source will we use for outdoor tiles? | Technical lead | Week 2 |
| Q4 | Who will own lift and ramp status updates after launch? | Team leader | Before release |
| Q5 | Will the university share official timetable data in future? | Team leader | Post-MVP |
| Q6 | What is the exact room-code format used across all buildings? | Data and QA lead | Week 2 |
| Q7 | How will we replace the simulated research with real responses? | Research lead | Before any real launch |

---

## 24. Appendix

### Appendix A: Survey questionnaire

1. What is your year of study?
2. Have you ever been lost or struggled to find a place on campus? (Yes / No)
3. How many times per semester have you been late because you could not find a venue? (Never / 1-2 / 3-5 / 6+)
4. What do you currently use to find places on campus? (Select all that apply)
5. How satisfied are you with current tools for finding rooms inside buildings? (1-5)
6. Rate the importance of each feature (1-5): indoor navigation, room search, accessible routes, next-class directions, offline use, shuttle times, live events, crowd indicators.
7. Which platform would you prefer? (Mobile app / Web app / No preference)
8. How likely are you to use a dedicated campus navigation app? (Very unlikely to Very likely)
9. Do you or someone you know need step-free routes? (Yes / No / Prefer not to say)
10. Do you usually have mobile data available on campus? (Always / Sometimes / Rarely)
11. What is the hardest place on campus to find?
12. What would make you trust a navigation app?
13. Any other feedback?

### Appendix B: Interview guide

**Introduction (2 min):** purpose, consent, anonymity, permission to take notes.

**Context (3 min):**
- Tell me about a typical day on campus.
- How do you usually find where you need to go?

**Experiences (8 min):**
- Describe the last time you struggled to find a place.
- What happened? How did you feel? What did you do?
- Have you been late because of this?

**Tools (3 min):**
- What tools or people do you rely on?
- What works well? What frustrates you?

**Accessibility (2 min, as relevant):**
- What do you need to know before planning a route?

**Concept reaction (3 min):**
- Show sketches; ask what is clear, confusing, missing.

**Close (1 min):** anything else, thanks.

### Appendix C: Glossary

| Term | Meaning |
|---|---|
| **PRD** | Product Requirements Document |
| **MVP** | Minimum Viable Product |
| **POI** | Point of interest (a room, office, facility) |
| **Graph** | Network of nodes (places) and edges (paths) used for routing |
| **Accessible route** | A route containing no stairs and using ramps or lifts |
| **MoSCoW** | Must, Should, Could, Won't prioritisation method |
| **SUS** | System Usability Scale, a standard usability questionnaire |
| **WCAG** | Web Content Accessibility Guidelines |

### Appendix D: Change log

| Version | Date | Description |
|---|---|---|
| 1.0 | 26 Nov 2026 | First complete PRD for BU-COS-209 |