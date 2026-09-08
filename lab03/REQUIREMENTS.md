# CampusPulse requirements

Name or team: Nino Matcharashvili

Date: 2026-09-08

Status: working draft

Use the source IDs `S1` to `S6` from the lab handout. Keep every requirement
short enough to test and trace.

## 1. Release scope

### In scope

List at least three capabilities that belong in the first release.

- University sign-in; browser/phone access for 5,000 students and 200 groups before Orientation Week.
- Verified groups, shared announcement drafts, and event/announcement publication by approved officers.
- Following groups, combined content discovery, RSVP, and private attendance by default.
- University-wide/members-only events and time/place correction notices.
- Reporting, immediate moderation, evidence/decision records, and appeals.
- Minimal personal data and deletion of cancelled-event attendance within 30 days.
- Should: duplicate-announcement control. Could: date filtering.

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

- FR-1 [Must] The system shall require university sign-in and deny campus access if sign-in fails or is absent. [Source: UR-10]
- FR-2 [Must] The system shall let students follow/unfollow groups and view their published announcements and events together, subject to FR-8/FR-13. [Source: UR-1]
- FR-3 [Must] The system shall allow one RSVP per student for an accessible, upcoming, non-cancelled event and allow withdrawal. [Source: UR-2]
- FR-4 [Must] The system shall make RSVPs private by default (A2), allow per-event opt-in to attendee visibility, and remove that visibility when the student opts out. [Source: UR-2]
- FR-5 [Must] The system shall allow only approved officers of the same group to create, save, and continue shared announcement drafts. [Source: UR-3]
- FR-6 [Must] The system shall reject a save if another officer changed the draft after it was loaded, showing a conflict and preserving the latest saved version. [Source: UR-3]
- FR-7 [Must] The system shall allow event creation and announcement/event publication only by approved officers of that verified group; other attempts are denied. [Source: UR-4, UR-9]
- FR-8 [Must] The system shall let only an event's approved group officers choose its university-wide or members-only audience and enforce that audience on listings, direct links, and RSVPs. Following does not grant membership. [Source: UR-5]
- FR-9 [Must] The system shall create correction notices for students whose RSVPs are current when an approved officer saves a change to their group's event time or place. Each notice display shall recheck FR-8/FR-13: authorized recipients see old/new details; others see only a generic change notice without event title, group, values, or link (A9). Notices meet NFR-5. [Source: UR-6, UR-5, UR-16]
- FR-10 [Must] The system shall let only Student Affairs grant/revoke verification, record the verifier and time, and display official badges only for currently verified groups. [Source: UR-9]
- FR-11 [Must] The system shall accept reports from users who can view the event, require a reason, and preserve the reported content, reason, reporter, and time for moderators. [Source: UR-7]
- FR-12 [Must] The system shall record who made each hide/appeal decision, the event, action, reason, and time; only moderators may access evidence and decision records. [Source: UR-17, UR-7]
- FR-13 [Must] The system shall let moderators hide events without prior reports or group approval, preserving event content and the reason as evidence. Hidden events disappear from ordinary listings/direct links and reject RSVPs; the group's officers receive the decision notice. [Source: UR-16, UR-7]
- FR-14 [Must] The system shall let approved officers submit reasoned appeals for their group's hidden events and let moderators review report/hiding evidence and decision history. Events stay hidden until a moderator records restoration; officers cannot restore them. [Source: UR-8]
- FR-15 [Must] The system shall limit personal information to A3 and collect no optional profile fields. [Source: UR-12]
- FR-16 [Must] The system shall let approved officers cancel their group's event, record cancellation time, reject new RSVPs, and delete attendance within NFR-1's deadline. [Source: UR-13, UR-4]
- FR-17 [Should] The system shall reject duplicate announcement publications by the same group within 10 minutes under A7, show a rejection message, and publish no duplicate. [Source: UR-14]
- FR-18 [Could] The system shall filter followed events by start date in the university timezone and restore the full permitted view when the filter is cleared. [Source: UR-15]

## 4. Non-functional requirements

Write at least four measurable quality requirements. State what is measured,
the target, and the condition under which the target applies. If you introduce
a number that is not in the handout, record it as an assumption or open
question in Section 8.

Format: `NFR-1 [Must] The system shall ... [Measure: target and condition] [Source: UR-1]`

- NFR-1 [Must] The system shall delete cancelled-event attendance within 30 days. [Measure: zero student-to-attendance records remain in system-controlled copies at cancellation + 30 days, including A6 records; appeals do not extend the deadline.] [Source: UR-13]
- NFR-2 [Must] The system shall support the pilot population. [Measure: with 5,000 student accounts and 200 groups loaded, authorized sign-in, following, publishing, RSVP, moderation/appeals, and cancellation workflows complete without capacity errors.] [Source: UR-10]
- NFR-3 [Must] The system shall support accessible phone-browser use. [Measure: all five A4 task scenarios complete using the named keyboard/screen-reader configurations; the 360 CSS-pixel layout needs no horizontal page scrolling. Targets are proposed in A4.] [Source: UR-11]
- NFR-4 [Should] The system shall display followed content and event details promptly. [Measure: p95 request-to-usable-display time is at most 2 seconds and unexpected failures at most 1% under A5 conditions; these are proposed targets.] [Source: UR-1, UR-10]
- NFR-5 [Must] The system shall make event-change notices available promptly. [Measure: under A5, notices exist for all students with an RSVP at correction time within 60 seconds of a successful save; this deadline is proposed.] [Source: UR-6]

## 5. User stories and acceptance criteria

Write at least three stories from different stakeholder viewpoints. Each story
needs at least two acceptance criteria. Across the set, include a failure,
permission boundary, privacy rule, or other non-happy path.

### US-1 [Source: S1, S5, UR-1, UR-2, UR-11, UR-15]

As a student attendee,

I want to find followed groups' events and manage my RSVP from my phone,

so that I can take part without exposing my attendance by default.

Acceptance criteria:

- AC-1.1: Following A/B shows their published, permitted content; unfollowing A removes its items. Hidden events and members-only events for non-members are absent. [FR-2, FR-8, FR-13]
- AC-1.2: A new RSVP is private; opt-in shows it to the event audience and opt-out hides it. Repeated submission creates no duplicate; withdrawal removes the RSVP. [FR-3, FR-4]
- AC-1.3: All A4 tasks complete with its keyboard/screen-reader configurations and no horizontal scrolling at 360 CSS pixels. [NFR-3]
- AC-1.4 [Could]: Selecting a date shows only permitted events starting that day; clearing it restores all dates. [FR-18]
- AC-1.5 [Should]: Under A5, p95 display time is at most 2 seconds and unexpected failures at most 1%. [NFR-4]

### US-2 [Source: S2, S3, UR-3, UR-4, UR-5, UR-6, UR-16]

As a group officer,

I want to collaborate on announcements and manage events for the intended audience,

so that our group can publish reliable information and communicate corrections.

Acceptance criteria:

- AC-2.1: Officer B can continue officer A's saved draft in their verified group. Outsiders cannot access/publish it; a stale save is rejected without overwriting the latest version. [FR-5, FR-6, FR-7]
- AC-2.2: For an upcoming, non-cancelled, non-hidden members-only event, a confirmed member can view/RSVP; a non-member cannot, even through a direct link. Other groups' officers cannot change its audience. [FR-8]
- AC-2.3: After a time/place correction, current RSVP recipients who still have access see old/new values within 60 seconds under A5; students who withdrew receive none. [FR-9, NFR-5]
- AC-2.4: A recipient who loses required membership or whose event is hidden sees only a generic notice, including when reopening an earlier notice. No event title, group, values, or link appears; NFR-5 still applies. [FR-8, FR-9, FR-13, NFR-5]

### US-3 [Source: S3, UR-7, UR-8, UR-16, UR-17]

As a campus moderator,

I want to investigate reports, hide harmful events, and review group appeals,

so that students are protected and decisions remain accountable.

Acceptance criteria:

- AC-3.1: Reports without reasons fail. Valid reports preserve content, reason, reporter, and time; ordinary users cannot read the evidence. [FR-11, FR-12]
- AC-3.2: Hiding an event, with or without a prior report, blocks ordinary listing/link/RSVP access, preserves evidence and the decision record, and notifies its officers. [FR-12, FR-13]
- AC-3.3: Officers can appeal but cannot restore hidden events. A moderator reviews evidence and records an uphold/restore decision; restored events keep their audience restrictions. [FR-8, FR-12, FR-14]

### US-4 [Source: S4, S6, UR-9, UR-10, UR-14]

As a Student Affairs representative,

I want a trustworthy pilot that serves the planned university community,

so that students can identify checked groups without impersonation or repeated posts undermining trust.

Acceptance criteria:

- AC-4.1: Officers cannot award official badges. Student Affairs verification records the verifier/time and shows a badge; revocation removes it and blocks new publication. [FR-7, FR-10]
- AC-4.2: With 5,000 accounts and 200 groups, authorized workflows listed in NFR-2 complete without capacity errors. Missing/failed sign-in denies campus access. [FR-1, NFR-2]
- AC-4.3 [Should]: Repeating an identical A7 announcement within 10 minutes is rejected; at or after 10 minutes it passes the duplicate check, subject to publication permission. [FR-17]

### US-5 [Source: S5, S3, UR-12, UR-13]

As a Data Protection Officer,

I want only necessary personal data retained for the stated service purposes,

so that cancelled-event attendance does not survive its deletion deadline.

Acceptance criteria:

- AC-5.1: Registration/workflows require only A3 fields, with no optional profile fields. Personal information submitted in report text follows A6. [FR-15]
- AC-5.2: Cancellation rejects new RSVPs. At cancellation + 30 days, no A6 attendance records remain, even during an unresolved appeal. [FR-16, NFR-1]

## 6. MoSCoW summary

List requirement or story IDs in every category. The Won't category must state
what is excluded from this release.

- Must: UR-1–UR-13, UR-16–UR-17; FR-1–FR-16; NFR-1–NFR-3, NFR-5; core criteria of US-1–US-5.
- Should: UR-14, FR-17, AC-4.3 (duplicate-announcement protection); NFR-4 and AC-1.5 (proposed response-time target). If capacity is limited, basic verified publishing/reporting remains Must; the precise automated duplicate policy and performance baseline can be renegotiated with S4/S2; S6 supplies abuse cases, not an approval role.
- Could: UR-15, FR-18, AC-1.4 (proposed date filter).
- Won't this release: native mobile apps; direct messages; external users, including anonymous public browsing; payments; video hosting; AI recommendations.

## 7. Traceability

Add at least four complete paths. Every row should connect evidence to a user
requirement, a system requirement, and a user story.

| Stakeholder need | User requirement | System requirement | User story |
|---|---|---|---|
| S1: stop checking multiple channels for followed groups | UR-1 | FR-2, NFR-4 | US-1, AC-1.1, AC-1.5 |
| S1/S5: attendance must start private | UR-2 | FR-3, FR-4 | US-1, AC-1.2 |
| S1: phone and screen-reader access | UR-11 | NFR-3 | US-1, AC-1.3 |
| S2: another officer can finish a draft | UR-3 | FR-5, FR-6 | US-2, AC-2.1 |
| S2: only approved officers publish | UR-4 | FR-7 | US-2, AC-2.1 |
| S2: members-only events stay within the group | UR-5 | FR-8, FR-9 | US-2, AC-2.2, AC-2.4 |
| S2/S3: tell RSVP'd students about corrections without exposing restricted or hidden event details | UR-6, UR-5, UR-16 | FR-9: current-access check; detailed or generic notice; NFR-5 | US-2, AC-2.3, AC-2.4 |
| S3: reports show what was reported and why | UR-7 | FR-11, FR-12 | US-3, AC-3.1 |
| S3: hide harmful events immediately with accountability | UR-16, UR-17 | FR-13, FR-12 | US-3, AC-3.2 |
| S3: preserve evidence for a group's appeal | UR-8, UR-7 | FR-14, FR-11, FR-13, FR-12 | US-3, AC-3.3 |
| S4/S6: an official badge means a group was checked | UR-9 | FR-10, FR-7 | US-4, AC-4.1 |
| S4: university-community pilot for 5,000 students/200 groups | UR-10 | FR-1, NFR-2 | US-4, AC-4.2 |
| S6: compromised accounts repeat announcements | UR-14 | FR-17 | US-4, AC-4.3 |
| S5: collect only necessary personal information | UR-12 | FR-15 | US-5, AC-5.1 |
| S5/S3: delete cancelled attendance without an appeal exception | UR-13 | FR-16, NFR-1 | US-5, AC-5.2 |
| S1: easier event discovery (team proposal) | UR-15 | FR-18 | US-1, AC-1.4 |

## 8. Assumptions and open questions

Separate decisions your team has assumed from questions that still need an
answer.

### Assumptions

- A1: Proposed: Student Affairs assigns verification/moderation roles and approves officers. Membership uses an approved roster. Verification revocation blocks new publication but does not automatically hide existing content.
- A2: Proposed: private RSVPs are visible only to the student and the event's approved officers. Opt-in shares the student's name/RSVP only with the event audience. Moderators have no routine attendance-list access.
- A3: Proposed necessary data: university ID/name (sign-in/attribution), role/membership (access), follows (content selection), RSVP/visibility (attendance), notice recipients (corrections), and reporter/decision identifiers, reasons, and times (accountability). No passwords or optional profiles.
- A4: Proposed checks: sign-in, follow, event discovery, RSVP/privacy, and reporting with Safari/VoiceOver on iPhone and keyboard-only Firefox on desktop; all tasks pass, with no horizontal scrolling at 360 CSS pixels. Supported versions remain Q6.
- A5: Proposed test: 100 signed-in users, 5,000 accounts and 200 groups, for 15 minutes; each user requests a feed or event every 5 seconds. Proposed targets: 2-second p95 and 1% unexpected errors. Test event corrections during the run; all current RSVP recipients must have an in-service notice within 60 seconds. The brief supplies no peak-traffic figure.
- A6: Proposed policy: delete all system-controlled attendance links by cancellation + 30 consecutive days, including withdrawn RSVPs, correction notices, exports, logs/backups, and copies in evidence. Preserve other appeal evidence; redact attendance links and prevent backup restoration of expired attendance. Confirm with S3/S5.
- A7: Proposed duplicate rule: identical title, body, and link from the same group within 10 minutes. At exactly 10 minutes the earlier post no longer blocks publication.
- A8: Date filtering is a Could proposal inferred from S1, not explicitly requested. Use the university timezone, to be confirmed with S4.
- A9: Proposed policy: notify current RSVP recipients, but check event access on every display. Denied recipients get a generic notice without event details. Confirm with S2/S3/S5.

### Open questions

- Q1 (S4): What is the Orientation Week deadline and available staffing?
- Q2 (S4): What peak traffic and content volumes are expected, and are A5 targets acceptable?
- Q3 (S3/S5): Which evidence must survive appeals, for how long, and how will attendance be redacted/deleted from backups within 30 days?
- Q4 (S2/S4): Who approves officers/members and verifies groups? Is A1’s revocation policy acceptable?
- Q5 (S1/S2/S3/S5): Are A2 access rules and A9 generic notices acceptable? Are in-service corrections sufficient, or is university email required?
- Q6 (S1/S4): Which browser/OS versions and assistive technologies must the pilot support?
- Q7 (S5): Are A3 fields necessary, and how long should non-cancelled attendance, accounts, follows, and other notifications remain?
