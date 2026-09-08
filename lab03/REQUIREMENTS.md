# CampusPulse requirements

Name or team: Nino Matcharashvili

Date: 2026-09-08

Status: working draft; proposed policies and quality targets need stakeholder confirmation.

Evidence: S1 student attendee; S2 group officer; S3 campus moderator; S4 Student Affairs;
S5 Data Protection Officer; S6 impersonation and repeated-post abuse cases.
The release brief additionally fixes university sign-in and a browser-based release.
Section 8 distinguishes team proposals from the supplied evidence.

## 1. Release scope

### In scope

- University sign-in and a browser-based pilot for 5,000 students and 200 groups before Orientation Week, including use from phone browsers.
- Group verification and official badges; shared announcement drafts and publishing by approved officers; event creation and publication.
- Following groups, a combined view of their announcements and events, and RSVP with private attendance by default.
- University-wide or members-only event visibility, event time/place corrections, and notices to students who RSVP'd.
- Reports, immediate event hiding by moderators, evidence and decision records, group appeals, and moderator restoration decisions (proposed policy from stakeholders.md Conflict 2).
- Minimal personal-data collection and deletion of cancelled-event attendance within 30 days.
- Should: blocking identical repeat announcements. Could: a date filter for followed events. Both are candidate improvements inside the above services, subject to capacity.

### Out of scope

- Native mobile apps.
- Direct messages.
- External users, including anonymous public event browsing.
- Payments.
- Video hosting.
- AI recommendations.

## 2. User requirements

- UR-1 [Must] Students need one place to follow groups and find their announcements and events. [Source: S1]
- UR-2 [Must] Students need their RSVP kept private unless they choose to share it. [Source: S1, S5]
- UR-3 [Must] Group officers need to continue announcement drafts started by another officer in their group. [Source: S2]
- UR-4 [Must] Groups need publishing to be restricted to their approved officers. [Source: S2]
- UR-5 [Must] Group officers need events to reach only the chosen university-wide or members-only audience. [Source: S2]
- UR-6 [Must] Students who RSVP need to learn about changes to an event's time or place. [Source: S2]
- UR-7 [Must] Moderators need reports that preserve what was reported and why. [Source: S3]
- UR-8 [Must] Groups need a way to appeal decisions to hide their events. [Source: S3]
- UR-9 [Must] University users need official badges to identify only groups checked by Student Affairs. [Source: S4, S6]
- UR-10 [Must] Student Affairs needs a university-community pilot for 5,000 students and 200 groups before Orientation Week. [Source: S4]
- UR-11 [Must] Students, including screen-reader users, need to complete the core activities from a phone browser. [Source: S1]
- UR-12 [Must] Students need their personal information limited to what CampusPulse requires to provide its services. [Source: S5]
- UR-13 [Must] The Data Protection Officer needs cancelled-event attendance data deleted within 30 days. [Source: S5]
- UR-14 [Should] The university community needs protection from repeated identical announcements by a compromised group account. [Source: S6]
- UR-15 [Could] Proposed: Students could narrow followed events to a chosen date. [Source: S1; proposed convenience, A8]
- UR-16 [Must] Campus moderators need to hide harmful events immediately. [Source: S3]
- UR-17 [Must] Campus moderators need a record identifying who made each moderation decision. [Source: S3]

## 3. Functional requirements

Write at least six observable system behaviours. Start each one with "The
system shall" and trace it to one or more user requirements.

Format: `FR-1 [Must] The system shall ... [Source: UR-1]`

- FR-1 [Must] The system shall
- FR-2 [Must] The system shall
- FR-3 [Must] The system shall
- FR-4 [Must] The system shall
- FR-5 [Must] The system shall
- FR-6 [Must] The system shall

## 4. Non-functional requirements

Write at least four measurable quality requirements. State what is measured,
the target, and the condition under which the target applies. If you introduce
a number that is not in the handout, record it as an assumption or open
question in Section 8.

Format: `NFR-1 [Must] The system shall ... [Measure: target and condition] [Source: UR-1]`

- NFR-1 [Must] The system shall
- NFR-2 [Must] The system shall
- NFR-3 [Should] The system shall
- NFR-4 [Must] The system shall

## 5. User stories and acceptance criteria

Write at least three stories from different stakeholder viewpoints. Each story
needs at least two acceptance criteria. Across the set, include a failure,
permission boundary, privacy rule, or other non-happy path.

### US-1 [Source: S?, UR-?]

As a <role>,

I want <capability>,

so that <benefit>.

Acceptance criteria:

-
-

### US-2 [Source: S?, UR-?]

As a <role>,

I want <capability>,

so that <benefit>.

Acceptance criteria:

-
-

### US-3 [Source: S?, UR-?]

As a <role>,

I want <capability>,

so that <benefit>.

Acceptance criteria:

-
-

## 6. MoSCoW summary

List requirement or story IDs in every category. The Won't category must state
what is excluded from this release.

- Must:
- Should:
- Could:
- Won't this release:

## 7. Traceability

Add at least four complete paths. Every row should connect evidence to a user
requirement, a system requirement, and a user story.

| Stakeholder need | User requirement | System requirement | User story |
|---|---|---|---|
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |

## 8. Assumptions and open questions

### Assumptions

- A8: Date filtering is inferred from S1's event-discovery need, not explicitly requested. Treat UR-15 as Could pending student feedback.

### Open questions

- Q1 (S4): What is the exact Orientation Week release date, expected peak traffic, and available delivery capacity? The 5,000 students and 200 groups describe the pilot population, not simultaneous use.
