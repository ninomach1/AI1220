# Plan — StudyMatch

## Process choice

### How stable and binding are the requirements?

The one-line brief leaves matching criteria, safety rules, and success measures undefined, so the requirements are not yet stable. They are likely to change as first-year students and the student council see the product in use.

### How quickly can real feedback arrive?

First-year students and student-council representatives can try a small working release and give feedback within each short sprint. This makes it practical to validate assumptions about useful matches early.

### What does failure cost?

A poor match mainly costs students time, and a limited campus pilot can be corrected quickly. Privacy and safety failures could cause greater harm, so every increment must meet the relevant safeguards before students use it.

### How many pieces must move together?

Matching, study preferences, session planning, and safety controls must eventually work together, but they can be delivered as small usable slices. The first slice can enforce first-semester same-college eligibility, support course-based discovery, and let students compare study goals and availability without requiring every later feature.

Verdict: Short increments, because requirements are uncertain, feedback is readily available, and useful slices can be delivered and adjusted safely.

## Milestones

| Milestone | When | What is true then |
|---|---|---|
| Sprint 1 review | 14 September 2026 | A student-council representative has demonstrated and approved same-college course-based partner discovery and preference comparison against the Sprint 1 acceptance criteria. |
| Limited campus pilot | 28 September 2026 | At least 30 first-year volunteers across three courses have used StudyMatch to attempt a study-partner search, and their outcomes have been recorded. |
| Pilot evaluation | 12 October 2026 | The client has reviewed a documented pilot report containing participation, successful-session, safety, and response-time results and has decided whether to expand the pilot. |

## Risks

| Risk | Likelihood | Mitigation |
|---|---|---|
| Too few first-year students join for useful matches to be available. | Medium | Recruit pilot volunteers through first-year course representatives now and ensure the pilot covers at least three courses before matching begins. |
| A student encounters harassment or unwanted disclosure of personal details. | Medium | Define approval-only contact sharing, exit, and reporting acceptance criteria now and require them to pass a safety review before the pilot. |
| Self-reported courses or availability produce irrelevant matches. | Medium | Test the matching assumptions in early student interviews and review failed-search feedback after every pilot session. |
