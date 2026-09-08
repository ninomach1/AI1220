# CampusPulse requirements

Name or team: Nino Matcharashvili

Date: 2026-09-08

Status: working draft

Use the source IDs `S1` to `S6` from the lab handout. Keep every requirement
short enough to test and trace.

## 1. Release scope

### In scope

List at least three capabilities that belong in the first release.

- University sign-in and browser/phone access for the 5,000-student/200-group pilot before Orientation Week.
- Verified groups, shared drafts, announcements/events, following, and RSVP.
- Audience restrictions, corrections, reports, moderation, evidence, and appeals.
- Minimal personal data; cancelled-attendance deletion within 30 days.

### Out of scope

List at least two explicit exclusions.

- Native mobile apps.
- Direct messages.
- External users, including anonymous public event browsing.
- Payments.
- Video hosting.
- AI recommendations.

## 2. User requirements

Write at least five customer-readable needs. Use one need per line and trace it
to the stakeholder evidence.

Format: `UR-1 [Must] ... [Source: S1]`

- UR-1 [Must] Students need one place to follow groups and find updates. [Source: S1]
- UR-2 [Must] Students need private RSVPs unless they opt in to sharing. [Source: S1, S5]
- UR-3 [Must] Officers need to continue each other's announcement drafts. [Source: S2]
- UR-4 [Must] Groups need publishing restricted to approved officers. [Source: S2]
- UR-5 [Must] Officers need university-wide or members-only event audiences. [Source: S2]
- UR-6 [Must] RSVP recipients need event time/place corrections. [Source: S2]
- UR-7 [Must] Moderators need reports preserving the content and reason. [Source: S3]
- UR-8 [Must] Groups need to appeal event-hiding decisions. [Source: S3]
- UR-9 [Must] Users need badges to identify only checked groups. [Source: S4, S6]
- UR-10 [Must] Student Affairs needs a 5,000-student/200-group pilot before Orientation Week. [Source: S4]
- UR-11 [Must] Students need phone-browser and screen-reader access. [Source: S1]
- UR-12 [Must] Students need personal-data collection limited to service needs. [Source: S5]
- UR-13 [Must] The Data Protection Officer needs cancelled attendance deleted within 30 days. [Source: S5]
- UR-14 [Should] Users need protection from repeated identical announcements. [Source: S6]
- UR-16 [Must] Moderators need to hide harmful events immediately. [Source: S3]
- UR-17 [Must] Moderators need records identifying each decision-maker. [Source: S3]

## 3. Functional requirements

Write at least six observable system behaviours. Start each one with "The
system shall" and trace it to one or more user requirements.

Format: `FR-1 [Must] The system shall ... [Source: UR-1]`

- FR-1 [Must] The system shall require university sign-in and deny failed or unauthenticated access. [Source: UR-10]
- FR-2 [Must] The system shall support following/unfollowing and show followed groups' published content, subject to FR-8/FR-13. [Source: UR-1]
- FR-3 [Must] The system shall allow one RSVP per student for an accessible, upcoming, non-cancelled event and allow withdrawal. [Source: UR-2]
- FR-4 [Must] The system shall default RSVPs to private (A2), allow per-event sharing, and hide shared attendance after opt-out. [Source: UR-2]
- FR-5 [Must] The system shall allow only a group's approved officers to create and continue its shared drafts. [Source: UR-3]
- FR-6 [Could] The system shall reject a save if another officer changed the draft since loading, preserving the newer version. [Source: UR-3]
- FR-7 [Must] The system shall allow only a verified group's approved officers to create events and publish its content. [Source: UR-4, UR-9]
- FR-8 [Must] The system shall let approved officers set their group's event audience and enforce it on listings, links, and RSVPs; following alone grants no membership. [Source: UR-5]
- FR-9 [Must] The system shall notify students whose RSVPs are current when approved officers save their group's event time/place changes, within NFR-5. Each notice display shall enforce FR-8/FR-13: show details if access is allowed, otherwise a generic notice without event details or links (A9). [Source: UR-6, UR-5, UR-16]
- FR-10 [Must] The system shall let only Student Affairs grant/revoke verification, recording the verifier/time; badges appear only while verified. [Source: UR-9]
- FR-11 [Must] The system shall accept reports from users with event access, require a reason, and preserve content, reason, reporter, and time. [Source: UR-7]
- FR-12 [Must] The system shall record moderator, event, action, reason, and time for hide/appeal decisions; evidence and records are moderator-only. [Source: UR-17, UR-7]
- FR-13 [Must] The system shall let moderators hide events immediately without prior reports/group approval, preserve evidence, block ordinary listing/link/RSVP access, and notify officers. [Source: UR-16, UR-7]
- FR-14 [Must] The system shall accept reasoned appeals from the affected group’s approved officers; only moderators may review evidence and restore events through recorded decisions. [Source: UR-8]
- FR-15 [Must] The system shall collect only A3 personal fields, with no optional profiles. [Source: UR-12]
- FR-16 [Must] The system shall let approved officers cancel their group's events, record cancellation time, block RSVPs, and delete attendance within NFR-1. [Source: UR-13, UR-4]
- FR-17 [Should] The system shall reject duplicate announcements under A7 and show a rejection message. [Source: UR-14]

## 4. Non-functional requirements

Write at least four measurable quality requirements. State what is measured,
the target, and the condition under which the target applies. If you introduce
a number that is not in the handout, record it as an assumption or open
question in Section 8.

Format: `NFR-1 [Must] The system shall ... [Measure: target and condition] [Source: UR-1]`

- NFR-1 [Must] The system shall delete cancelled attendance. [Measure: zero attendance links remain in system-controlled copies after 30 days from cancellation, including A6; no appeal exception.] [Source: UR-13]
- NFR-2 [Must] The system shall support the pilot. [Measure: sign-in, publishing, following, RSVP, reporting, moderation/appeals, and cancellation succeed with 5,000 accounts and 200 groups loaded.] [Source: UR-10]
- NFR-3 [Must] The system shall support accessible phone use. [Measure: all A4 tasks complete under both configurations; no horizontal scrolling at 360 CSS pixels (proposed).] [Source: UR-11]
- NFR-4 [Should] The system shall display followed content/event details quickly. [Measure: 95% of requests display usable content within 2 seconds under A5 (proposed).] [Source: UR-1, UR-10]
- NFR-5 [Must] The system shall provide correction notices. [Measure: all current RSVP recipients have a notice within 60 seconds of saving a correction under A5 (proposed).] [Source: UR-6]

## 5. User stories and acceptance criteria

Write at least three stories from different stakeholder viewpoints. Each story
needs at least two acceptance criteria. Across the set, include a failure,
permission boundary, privacy rule, or other non-happy path.

### US-1 [Source: S1, S5, UR-1, UR-2, UR-13]

As a student,

I want to find events and manage my RSVP,

so that I can participate privately.

Acceptance criteria:

- AC-1.1: Following shows permitted group updates; unfollowing removes them. Hidden events stay inaccessible to ordinary users; members-only events stay inaccessible to non-members. [FR-2, FR-8, FR-13]
- AC-1.2: RSVP starts private; opt-in/out changes sharing. Cancellation deletes all A6 attendance links within 30 days. [FR-4, FR-16, NFR-1]

### US-2 [Source: S2, S3, S4, S6, UR-3, UR-4, UR-5, UR-6, UR-9, UR-16]

As a group officer,

I want to publish reliable group updates,

so that the intended audience receives correct information.

Acceptance criteria:

- AC-2.1: Approved officers share drafts and publish for their verified group; unauthorized publishing fails. A badge appears only after Student Affairs verification. [FR-5, FR-7, FR-10]
- AC-2.2: Corrections reach current RSVP recipients within 60 seconds under A5. On every display, recipients without event access see only a generic notice without details/links. [FR-9, NFR-5]

### US-3 [Source: S3, UR-7, UR-8, UR-16, UR-17]

As a moderator,

I want to investigate reports and appeals,

so that harmful events can be hidden with accountable decisions.

Acceptance criteria:

- AC-3.1: Reports require a reason. Hiding blocks ordinary event access while preserving evidence and the decision-maker record. [FR-11, FR-12, FR-13]
- AC-3.2: Officers may appeal but cannot restore events; moderator review records the outcome and any restoration respects the event audience. [FR-8, FR-12, FR-14]

## 6. MoSCoW summary

List requirement or story IDs in every category. The Won't category must state
what is excluded from this release.

- Must: UR-1–UR-13, UR-16–UR-17; FR-1–FR-5, FR-7–FR-16; NFR-1–NFR-3, NFR-5; US-1–US-3.
- Should: UR-14, FR-17 (duplicate control); NFR-4 (response time).
- Could: FR-6 (conflicting draft-save protection).
- Won't this release: native apps, direct messages, external/anonymous users, payments, video hosting, AI recommendations.

## 7. Traceability

Add at least four complete paths. Every row should connect evidence to a user
requirement, a system requirement, and a user story.

| Stakeholder need | User requirement | System requirement | User story |
|---|---|---|---|
| S1: combined group updates | UR-1 | FR-2 | US-1 |
| S1/S5: private RSVP and cancelled-attendance deletion | UR-2, UR-13 | FR-4, NFR-1 | US-1 |
| S2: shared, approved publishing | UR-3, UR-4 | FR-5, FR-7 | US-2 |
| S2/S3: corrections respect current access | UR-6, UR-5, UR-16 | FR-9: detailed or generic notice after access check; NFR-5 | US-2, AC-2.2 |
| S3: evidence and accountable appeals | UR-7, UR-8, UR-17 | FR-11, FR-12, FR-14 | US-3 |
| S4/S6: checked groups have official badges | UR-9 | FR-10 | US-2 |

## 8. Assumptions and open questions

Separate decisions your team has assumed from questions that still need an
answer.

### Assumptions

- A1: Proposed: Student Affairs assigns roles/approves officers; membership uses an approved roster. Verification revocation blocks new publication.
- A2: Proposed: private RSVPs are visible only to the student and event officers; sharing exposes names only to the event audience.
- A3: Proposed fields: university ID/name, roles/membership, follows, RSVP/visibility, notice recipients, and report/decision authors, reasons, and times; only for the associated services.
- A4: Proposed tasks: sign-in, follow, find events, RSVP/privacy, report; test with iPhone Safari/VoiceOver and desktop Firefox/keyboard. Proposed width: 360 CSS pixels.
- A5: Proposed load: 100 sessions, pilot-size accounts/groups, one feed/event request per user every 5 seconds for 15 minutes. Targets: 2-second p95 and 60-second notices. Actual peak is unknown.
- A6: Proposed policy: delete all cancelled-attendance links, including withdrawn RSVPs, notices, logs/backups, exports, and evidence copies. Preserve other appeal evidence; never restore expired attendance.
- A7: Proposed duplicate rule: identical title/body/link from the same group within 10 minutes; at 10 minutes the restriction expires.
- A9: Proposed: check access whenever notices display; denied recipients get a generic notice without event details/links.

### Open questions

- Q1 (S4): What is the exact deadline and available staffing?
- Q2 (S4): What peak traffic is expected; are A5 targets acceptable?
- Q3 (S3/S5): Which appeal evidence must remain, for how long, and how will A6 deletion/redaction work?
- Q4 (S2/S4): Who approves officers/members and verifies groups?
- Q5 (S1/S2/S3/S5): Are A2/A9 acceptable; are in-service notices sufficient?
- Q6 (S1/S4): Which browser/OS versions and assistive technologies are required?
- Q7 (S5): Are A3 fields necessary; how long should other personal data remain?
