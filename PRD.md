# Product Requirements Document (PRD)

## Quadrant: Campus Navigation System for Babcock University

**Course:** BU-COS-209 (Backend Engineering)
**Team:** Group _[number]_
**Members:** _[Uzoma David Chisom (25/0970.)]_, _[Osowe Marvelous Ayodele  (25/1127.)]_, _[Omeka Divine Ekenechuckwu  (25/2322.)]_, _[Osindero Iyanulolu Samuel (25/1602.)]_
**Version:** 1.0
**Date:** November 26th, 2026

---

## 1. Overview

Quadrant is a campus navigation system that helps students, lecturers, staff, and visitors find their way around Babcock University quickly and confidently. It replaces the current mix of asking other people, relying on personal memory, and unclear signboards with one place to search for a location, see it on a map, and follow step-by-step directions from where they are standing.

## 2. Problem Statement

Finding the right lecture hall, office, or faculty on campus is harder than it should be, especially for newer students. There is no single, reliable, digital source of campus directions, so people depend on other people and on guesswork.

Based on our survey of 14 Babcock University students, the problem has three core parts:

1. **Difficulty finding locations.** 78.6% of respondents have difficulty finding locations on campus at least sometimes (64.3% "sometimes", 14.3% "yes").
2. **Lateness.** 85.7% have arrived late for a lecture or appointment because they could not locate the venue (57.1% "yes", 28.6% "sometimes").
3. **Wasted time and unclear guidance.** "Wasting time looking for locations" (28.6%), "lack of proper directions" (21.4%), and "poor or unclear signboards" (21.4%) were the biggest challenges named.

## 3. Who Has This Problem? (Target Users)

### Primary users
- **Students:** new students still learning the campus, and returning students who need to find unfamiliar venues for lectures, offices, and faculties.

### Secondary users
- **Lecturers and non-academic staff:** need to reach venues and direct visitors.
- **Visitors and guests:** need to reach offices, events, or the chapel without asking several people.
- **Users with mobility needs:** need to know which routes are step-free.

> The survey sampled students only. The secondary users above are design assumptions to be validated in later research.

### User personas

| Persona | Description | Main pain point |
|---|---|---|
| New student | Recently resumed, still learning where buildings are, relies on other students | Gets lost and arrives late to lectures |
| Returning student | Knows the main areas but needs to find new venues, offices, and faculties | Wastes time finding unfamiliar locations |
| Visitor | Comes for a meeting or event with no knowledge of the campus | Has to ask multiple people, unclear signboards |
| Student with mobility needs | Needs step-free paths between classes | No information on accessible routes |

## 4. How Users Cope Today

Based on survey responses to "How do you currently find your way around campus?":

| Current method | Share of respondents |
|---|---|
| Asking other students | 35.7% (5 of 14) |
| Personal knowledge of the campus | 35.7% (5 of 14) |
| Other | 14.3% (2 of 14) |
| Asking security personnel | 7.1% (1 of 14) |
| Other written answer ("Yes") | 7.1% (1 of 14) |
| Using signboards | 0% |
| Google Maps | 0% |

**Consequences:** lost time searching for locations, being late to lectures and appointments, and constantly depending on other people for directions. 50% of respondents need to ask someone for directions at least occasionally, and 28.6% do so often or very often.

## 5. Why Existing Solutions Fall Short

| Existing solution | Limitation |
|---|---|
| Asking other students | Depends on who is nearby, answers are inconsistent, not available to visitors or newcomers who know nobody |
| Personal knowledge | Only works after months on campus; new students and visitors do not have it |
| Asking security personnel | Slow, not always nearby, not scalable |
| Signboards | 21.4% name poor or unclear signboards as their biggest challenge, and no respondent uses signboards to find their way |
| Generic map apps (e.g. Google Maps) | Not used by any respondent. Coverage of internal campus paths, faculties, and lecture halls is to be verified by the team |

**Gap:** there is no campus-specific digital tool that lets someone search for a Babcock location and get step-by-step directions from their current position.

## 6. Research Approach & Findings

### 6.1 Method
- **Online survey (Google Forms):** 18 questions, 14 responses
- **Respondents:** 100% students; 92.9% 200 Level and 7.1% 100 Level; 85.7% have been at Babcock between 6 months and 1 year
- **Interviews:** not conducted. This PRD relies on the survey only.

### 6.2 Survey results

**Is there a problem?**

| Question | Result |
|---|---|
| Q4. Difficulty finding locations on campus? | Sometimes 64.3% (9), No 21.4% (3), Yes 14.3% (2) |
| Q7. Arrived late because venue could not be located? | Yes 57.1% (8), Sometimes 28.6% (4), No 14.3% (2) |
| Q8. How often do you need to ask for directions? | Rarely 35.7% (5), Occasionally 21.4% (3), Often 14.3% (2), Very often 14.3% (2), Never 14.3% (2) |

**Where and why?**

| Question | Result |
|---|---|
| Q5. Hardest locations to find (multiple selections) | Lecture halls 28.6% (4), Administrative offices 28.6% (4), Faculties and departments 28.6% (4), Church/Chapel 14.3% (2), Hostels 7.1% (1), Other 21.4% (3), Cafeterias 0%, Sports facilities 0% |
| Q9. Biggest challenge | Wasting time looking for locations 28.6% (4), Lack of proper directions 21.4% (3), Poor or unclear signboards 21.4% (3), Unfamiliarity with campus locations 14.3% (2), Other 14.3% (2), Difficulty identifying buildings 0% |

**Interest in a solution**

| Question | Result |
|---|---|
| Q10. Would a digital campus navigation system be useful? | Yes 85.7% (12), Maybe 7.1% (1), No 7.1% (1) |
| Q11. Would you use a mobile or web app to locate places? | Yes 85.7% (12), Maybe 14.3% (2), No 0% |
| Q16. How much would it improve movement around campus? | Extremely helpful 64.3% (9), Very helpful 28.6% (4), Slightly helpful 7.1% (1) |

**Features and platform**

| Question | Result |
|---|---|
| Q12. Desired features (multiple selections) | Step-by-step directions 71.4% (10), Interactive campus map 64.3% (9), Search for buildings and locations 50% (7), Estimated walking distance and time 42.9% (6), Search for lecture halls 35.7% (5), Locate faculties and departments 21.4% (3), Locate hostels and cafeterias 21.4% (3), Emergency locations (clinic, security) 21.4% (3), Voice navigation 14.3% (2) |
| Q13. Directions based on current location? | Yes 100% (14) |
| Q14. Is offline navigation important? | Yes 85.7% (12), Maybe 14.3% (2), No 0% |
| Q15. Preferred platform | All of the above (Android, iOS, website) 85.7% (12), Website 14.3% (2) |

**Open-ended responses**

- Q17 (additional features, 4 responses): "scooters"; "I cant say"; "Locating where other members of my department are would be really cool."; "Things like how to locate missed items"
- Q18 (other suggestions, 5 responses): no substantive suggestions

### 6.3 Key findings

| Finding | Evidence | Product implication |
|---|---|---|
| Getting lost is common and causes lateness | 78.6% have difficulty finding locations; 85.7% have been late | Fast search and clear directions are the core of the MVP |
| Lecture halls, admin offices, and faculties are hardest to find | 28.6% each (Q5) | Load these location types into the system first |
| People rely on other people, not tools | Asking students and personal knowledge are 35.7% each; signboards and Google Maps 0% (Q6) | Quadrant should work for people with no local knowledge |
| Users want guidance, not just a map | Step-by-step directions 71.4%, interactive map 64.3% (Q12) | Both are Must-have MVP features |
| Directions must start from where the user is | 100% want current-location directions (Q13) | Current location is the default start point, with manual fallback |
| Walking time matters | 42.9% want walking distance and time (Q12) | Show distance and estimated time on every route |
| Offline use is valued | 85.7% say offline navigation is important (Q14) | Offline support is a Should-have, cached map is a stretch goal |
| Demand is strong | 85.7% say useful; 92.9% say very or extremely helpful (Q10, Q16) | Validates building the product |
| Users want one product on every device | 85.7% want Android, iOS, and website (Q15) | Responsive web app as the primary platform |
| Emergency locations wanted by some | 21.4% (Q12) | Include clinic and security as location categories |

### 6.4 Limitations and assumptions still to validate
- The sample is small (n = 14), informal, and made up entirely of students, mostly at 200 Level. Results are indicative, not statistically representative.
- Lecturers, non-academic staff, visitors, and users with mobility needs were not surveyed.
- The survey did not ask about accessibility, so accessible routing is a design decision based on inclusion, to be validated in usability testing.
- Single mentions in the open-ended responses (department member locator, lost-and-found, scooters) are ideas, not evidence of demand.
- Whether Google Maps adequately covers the Babcock campus has not been tested by the team.

## 7. Proposed Solution

Quadrant is a web platform (with a mobile-friendly interface) offering:

- **Search for locations:** buildings, lecture halls, administrative offices, faculties, departments, and key services
- **Interactive campus map:** locations shown as markers with the user's current position
- **Step-by-step walking directions:** from the user's current location (or a chosen starting point) to the destination
- **Distance and estimated walking time:** shown for every route
- **Location details:** name, description, category, and entrance information
- **Emergency locations:** clinic and security points easy to find
- **Accessible-route option:** step-free routing where path data supports it
- **Admin management:** authorized admins keep location and path data accurate

## 8. Goals & Success Metrics

| Goal | Metric | Target |
|---|---|---|
| Fast discovery | Time for a first-time user to find a destination | Under 30 seconds |
| Reliable guidance | Task success rate in usability tests | 90% or higher |
| Fewer late arrivals | Share of users late because they could not find a venue | Lower than the survey baseline (85.7% late at least sometimes, n = 14) |
| Accuracy | Walking-time estimate vs. real walk | Within 2 minutes |
| Adoption | Users in pilot | _[e.g. 100 students]_ |
| Data coverage | Locations loaded | _[e.g. 30 priority locations]_ |
| Satisfaction | Ease-of-use rating | 4.0 / 5 or higher |

## 9. MVP Definition

The Minimum Viable Product focuses only on solving the core problem: **find a campus location and get directions to it.**

### In scope (MVP)
- Interactive campus map with location markers
- Search for buildings, lecture halls, administrative offices, and faculties
- Location detail page (name, description, category, entrance)
- Walking route from current location (or chosen start point) to destination
- Step-by-step directions with distance and estimated walking time
- Emergency locations (clinic, security) as a browsable category
- Basic admin management of locations and path data (add, edit, remove)
- No account required for students and visitors

### Out of scope (future versions)
- Full offline mode (a cached campus map is a stretch goal)
- Voice navigation
- Indoor, room-level navigation
- User accounts and favorites
- Live path-closure updates
- Lost-and-found locator
- Department-member locator
- Native mobile apps

## 10. Functional Requirements

| ID | Requirement | Priority |
|---|---|---|
| FR-1 | Users can view an interactive campus map with location markers | Must |
| FR-2 | Users can search locations by name, category, or keyword | Must |
| FR-3 | Users can view location details | Must |
| FR-4 | System gets the user's current location when permitted | Must |
| FR-5 | System generates a walking route between two campus points | Must |
| FR-6 | System shows step-by-step directions, distance, and estimated walking time | Must |
| FR-7 | Users can choose a starting point manually | Must |
| FR-8 | Admin can add, edit, and remove locations and path data | Must |
| FR-9 | Users can browse locations by category (including emergency locations) | Should |
| FR-10 | Accessible-route option avoiding stairs | Should |
| FR-11 | Search suggestions and alternative names for locations | Should |
| FR-12 | Admin can mark paths as closed | Should |
| FR-13 | Users can report incorrect or missing information | Could |
| FR-14 | Users can save favorite locations | Could |
| FR-15 | Offline use of cached map and routes | Should (stretch for MVP) |
| FR-16 | Lost-and-found locator, department-member locator, voice navigation | Could (post-MVP) |

## 11. Non-Functional Requirements

- **Performance:** search results in under 1 second; route calculation in under 3 seconds
- **Usability:** mobile-first, usable by a first-time user without instructions, works on low bandwidth
- **Availability:** target 99% uptime during campus hours
- **Accuracy:** location and path data verified by walking the campus before release
- **Security:** role-based admin access, hashed admin passwords, input validation
- **Privacy:** location used only for navigation, not stored or shared; comply with applicable data protection rules (e.g. NDPA in Nigeria)
- **Compatibility:** works on common Android, iOS, and desktop browsers
- **Maintainability:** campus data stored in the database, not in code, so it can be updated without redeploying

## 12. User Stories

- As a **student**, I want to search for a lecture hall by name so that I can find it before class starts.
- As a **new student**, I want step-by-step directions from where I am so that I do not have to ask other people.
- As a **student**, I want to see the estimated walking time so that I know when to leave to arrive on time.
- As a **visitor**, I want to find an administrative office without creating an account so that I can get started immediately.
- As a **user**, I want to find the clinic or security post quickly in an emergency.
- As a **user with mobility needs**, I want a step-free route option so that I avoid stairs.
- As an **admin**, I want to add and update locations so that the map stays accurate.

## 13. High-Level Technical Considerations

> _Per the assignment, the problem is researched first. The stack below is tentative and open to discussion._

- **Frontend:** responsive web app (85.7% of respondents want Android, iOS, and web access) _[framework TBD by team]_
- **Backend:** REST API serving locations, search, and route calculation, with role-based access for admin endpoints _[language and framework TBD]_
- **Database:** relational database for locations, categories, and the campus path graph
- **Routing:** campus paths modelled as a graph (nodes and edges) with a shortest-path algorithm; edges flagged accessible or not for accessible routing
- **Location service:** browser geolocation, with manual start point as fallback
- **Hosting:** _[TBD]_

### Core data entities
`Location`, `Category`, `Node`, `PathSegment`, `Admin`, `Report` (optional), `Favorite` (post-MVP)

### Main API endpoints (draft)
- `GET /locations` and `GET /locations/{id}`: list, search, and view details
- `GET /categories`: browse by category
- `GET /route?from=&to=&accessible=`: calculate a route
- `POST/PUT/DELETE /admin/locations`: admin management (authenticated)
- `PUT /admin/paths/{id}`: update or close a path (authenticated)

## 14. Risks & Mitigations

| Risk | Impact | Mitigation |
|---|---|---|
| Inaccurate or incomplete campus and path data | Wrong directions, loss of trust | Walk-test key routes; start with priority locations; show last-verified date |
| GPS inaccuracy near buildings | Wrong start point | Allow manual start selection; use clear landmarks |
| Small, student-only survey sample | Findings may not apply to other users | State limitations; validate with staff, visitors, and users with mobility needs in testing |
| Accessibility path data is wrong | Users sent on unsuitable routes | Verify accessible features on site before enabling the option |
| Tight timeline and limited team time | Unfinished MVP | Strict MVP scope; cut Should and Could items first |
| Privacy concerns about location | Legal and trust risk | Do not store location; ask permission with a clear explanation |

## 15. Timeline (Proposed)

| Phase | Activity | Duration |
|---|---|---|
| 1 | Research (survey, 14 responses) | Done |
| 2 | Design and database schema | _[Week 1]_ |
| 3 | MVP backend build (API, routing, admin) | _[Week 5]_ |
| 4 | Campus data collection and walk-testing | _[Week 6-8]_ |
| 5 | Usability testing with students (and staff or visitors if possible) | _[Week 9]_ |
| 6 | Iterate and plan v2 | _[Week 10]_ |

## 16. Open Questions

- Which language, framework, and hosting will the team use?
- Where will campus map and path data come from, and who verifies it?
- How will accessible routes be verified on site?
- Will a cached offline map be possible within the MVP timeline?
- Who will maintain the location data after the course ends?
- Should department-member and lost-and-found features be explored later, given the privacy implications of the first?

---

_End of document_