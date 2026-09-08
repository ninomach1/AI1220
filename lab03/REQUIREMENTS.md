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

- FR-1 [Must] The system shall require a valid university sign-in before granting access to campus content or actions, and deny access when sign-in fails or is absent. [Source: UR-10]
- FR-2 [Must] The system shall let a signed-in student follow or unfollow a group and show published announcements and events from followed groups in a combined view, subject to FR-8 and FR-13. [Source: UR-1]
- FR-3 [Must] The system shall let a student RSVP to an accessible, upcoming, non-cancelled event or withdraw that RSVP; repeated RSVP submissions shall create only one current attendance record for that student and event. [Source: UR-2]
- FR-4 [Must] The system shall create each RSVP as private and show a student's RSVP to other attendees only after that student opts in for that event; withdrawal of the opt-in shall remove it from other attendees' views. Private RSVP access shall follow A2. [Source: UR-2]
- FR-5 [Must] The system shall let approved officers in the same group create, save, and continue shared announcement drafts, and deny draft access to other students and officers of other groups. [Source: UR-3]
- FR-6 [Must] The system shall reject a draft save when another officer has changed the stored version since the saving officer loaded it, with a conflict message while retaining the latest saved version, so one officer cannot silently overwrite another officer's changes. [Source: UR-3]
- FR-7 [Must] The system shall let approved officers create events and publish their group's announcements and events only while the group's verification is current; a non-approved officer, officer of another group, or officer of an unverified group shall receive a denial with no publication. [Source: UR-4, UR-9]
- FR-8 [Must] The system shall let an approved officer of an event's group choose university-wide or members-only visibility for that event, deny visibility changes by other users, and restrict its listing, details, and RSVP action to the chosen audience, including when accessed by a direct link. Following alone shall not grant membership. [Source: UR-5]
- FR-9 [Must] The system shall let approved officers correct their own group's event time or place and create an in-service notice for each student with a current RSVP when the correction is saved, showing the old and new values. The notice deadline is NFR-5. [Source: UR-6]
- FR-10 [Must] The system shall allow only Student Affairs verifiers to grant or revoke a group's verified status, record the verifier and decision time, and display an official badge only while that status is current. User-supplied group names or content shall not grant official status. [Source: UR-9]
- FR-11 [Must] The system shall accept a report from a signed-in user who can view an event only when a non-empty reason is supplied, and save the reported event content, reason, reporter identity, and submission time for moderators. [Source: UR-7]
- FR-12 [Must] The system shall record the moderator identity, event, action, reason, and timestamp for each hide or appeal decision, deny ordinary users access to report evidence and decision records, and prevent group officers from altering those records. [Source: UR-17, UR-7]
- FR-13 [Must] The system shall let a moderator hide an event without awaiting group approval or a prior user report, saving the event content and moderator reason as evidence if no report exists; once the action succeeds, ordinary users shall no longer see it in listings or through direct links and shall be unable to RSVP, while moderators retain evidence access and the group's approved officers receive a decision notice. [Source: UR-16, UR-7]
- FR-14 [Must] The system shall let approved officers appeal a decision concerning their group's hidden event with a non-empty explanation, present the report evidence and decision history to a moderator for review, and keep the event hidden until a moderator records a decision to restore it; an officer's direct restoration attempt shall be denied. [Source: UR-8]
- FR-15 [Must] The system shall limit required personal information to the fields and service purposes in A3 and collect no optional personal profile fields for the pilot. [Source: UR-12]
- FR-16 [Must] The system shall let an approved officer cancel their own group's event, record the cancellation time, and reject new RSVPs after cancellation; its attendance records shall be deleted within the NFR-1 deadline. [Source: UR-13, UR-4]
- FR-17 [Should] The system shall reject a second announcement publication whose title, body, and link exactly match one published by the same group within the preceding 10 minutes, report the rejection to the officer, and create no additional published announcement. The proposed comparison and threshold are A7. [Source: UR-14]
- FR-18 [Could] The system shall let a student filter the followed-events view to events starting on a selected date in the university's local timezone, and clear that filter to restore the full audience-permitted view. [Source: UR-15]

## 4. Non-functional requirements

- NFR-1 [Must] The system shall delete cancelled-event attendance data by 30 days after cancellation. [Measure: zero retained records linking a student to that event's attendance at cancellation time + 30 days, checked across operational stores, exports, logs, and backups under A6; an appeal does not extend the deadline.] [Source: UR-13]
- NFR-2 [Must] The system shall support the stated pilot population. [Measure: with 5,000 student accounts and 200 group records loaded, all retained fixture records remain retrievable only as permitted by their access rules (deleted attendance is excluded) and the Must acceptance scenarios for sign-in, following, publication, RSVP, reporting, moderation, appeals, and cancellation complete without capacity errors; these counts do not specify concurrent traffic.] [Source: UR-10]
- NFR-3 [Must] The system shall make the core student tasks usable with the proposed assistive and mobile configurations in A4. [Measure: 100% of sign-in, follow, event discovery, RSVP/privacy change, and reporting scenarios can be completed using keyboard-only desktop input and using the named phone screen reader; at a 360 CSS-pixel viewport, each task is also possible without horizontal page scrolling. Configuration and coverage targets are proposals.] [Source: UR-11]
- NFR-4 [Should] The system shall display followed content and event details within the proposed response-time target. [Measure: the 95th percentile time from a user request until usable content is displayed is at most 2 seconds over a 15-minute run after a 2-minute warm-up, with the pilot dataset, 100 active sessions, and the workload/network conditions in A5; unexpected request failures are at most 1%. These are assumed test conditions, not a supplied peak forecast.] [Source: UR-1, UR-10]
- NFR-5 [Must] The system shall make saved event time/place corrections available to affected students promptly. [Measure: in the A5 workload, a readable in-service notice exists for 100% of the students with a current RSVP at correction time within 60 seconds of each successful save; deadline and test load are proposed in A5.] [Source: UR-6]

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

These are proposed team decisions, not facts supplied by the stakeholders. Numbers
other than 5,000 students, 200 groups, and the 30-day cancellation deadline require
confirmation. Acceptance scenarios describe future checks; no product has been built or tested.

- A1: Student Affairs appoints verifiers and moderators and authorizes group officers. Group membership is an approved roster, not the follow list. Only verified groups may publish; revocation removes the badge and blocks new publications without automatically hiding existing content. The brief's university sign-in excludes anonymous/public access. Validate these policies with S2/S4.
- A2: An RSVP is private to the student and that event's approved group officers for event administration. Moderators have no routine attendance-list access. Opt-in exposes only that student's name/RSVP to the event's permitted audience; opt-out removes it. Report evidence and decision records are restricted to moderators; officers receive their own group's decision notice and can submit an appeal. Confirm these access purposes with S1/S3/S5.
- A3: Proposed personal-data inventory: university account identifier (sign-in and attribution), university display name (officer attribution or an opted-in RSVP), role and group-membership links (authorization), follows (personalized content), RSVP/event link and visibility choice (attendance), reporter identifier and submitted reason (report follow-up), and actor identifiers/reasons/timestamps in moderation and verification decisions (accountability). No passwords are stored by CampusPulse. Notification recipient identifiers support corrections. No additional profile data is collected. Text may contain personal information, so A6 applies to copied attendance data as well; S5 must approve this inventory and retention periods.
- A4: Proposed accessibility check configurations: Safari with VoiceOver on an iPhone; Firefox with keyboard-only navigation on desktop; a 360 CSS-pixel phone viewport. Record exact supported OS/browser versions in the release test plan. Proposed target: 100% of the five named NFR-3 task scenarios complete; this is a practical acceptance proposal, not a claim of compliance with an unstated accessibility standard. Include screen-reader users in validation.
- A5: Proposed performance fixture: 5,000 accounts, 200 groups, 2,000 published events, 4,000 announcements, and 20,000 RSVP records. Run 100 authenticated sessions for 15 minutes after 2 minutes of warm-up, each starting one action every 5 seconds; action mix: 60% followed-view reads, 30% event-detail reads, 5% RSVP changes, and 5% time/place corrections by authorized officers. Use a 360 CSS-pixel client viewport, 10 Mbps downstream/2 Mbps upstream and 100 ms round-trip latency; record browser/device/server configuration with results. The 2-second p95, 1% error ceiling, and 60-second notice deadline are proposed baselines. Notices are durable in-service items readable on the student's next sign-in; the deadline measures availability, not whether a student reads them. Corrections are distinct from direct messages. These assumptions do not establish Orientation Week's actual peak.
- A6: Thirty days means 30 consecutive 24-hour periods from the stored cancellation timestamp. Attendance includes current and withdrawn RSVP records, attendance exports, attendance identifiers in logs/backups, and any copied student-to-attendance links in evidence. Do not copy attendance lists into report evidence; if present, remove or redact their attendance links by the same deadline, leaving event content, report reason, and decision evidence to the extent these contain no attendance link. Backup handling must not restore expired attendance. Confirm this proposed privacy/evidence policy with S3/S5 before implementation; Q3 remains unresolved.
- A7: Proposed repeat-post rule: exact equality of the submitted title, body, and link for the same group within a rolling 10-minute interval; at exactly 10 minutes the old post is outside the interval. This is a bounded duplicate control, not protection against modified spam or every phishing attempt. Ask S2/S4 to approve the threshold and permitted legitimate repeats.
- A8: Date filtering is inferred from S1's event-discovery need, not explicitly requested. Treat it as Could pending student feedback. Use the university's configured local timezone for the selected calendar date; confirm that timezone with S4.

### Open questions

- Q1 (S4): What is the exact Orientation Week release date, and what staffing and delivery time are available for the pilot? The source gives a deadline name but no calendar date.
- Q2 (S4): What peak concurrent users, request rate, expected event/RSVP volumes, client/network conditions, and correction-notice latency should we plan for at Orientation Week? Can A5's provisional targets be accepted or revised?
- Q3 (S3/S5): Which report/evidence fields must survive an appeal, how should attendance embedded in a report or event be redacted, what appeal window and evidence-retention period apply, and what backup-deletion policy meets the 30-day attendance deadline? No attendance-retention exception is assumed.
- Q4 (S2/S4): Who approves or revokes officers and group membership, what evidence verifies a group, and should existing content be hidden automatically when verification is revoked? Confirm A1's proposed pilot behavior.
- Q5 (S1/S2/S5): Are A2's officer access and optional name visibility acceptable, and does an in-service correction notice meet the need to tell students, or is a university email notice also required? What should happen to an RSVP if membership is revoked before a correction to a members-only event?
- Q6 (S1/S4): Which browser/OS versions, assistive technologies, and additional accessibility criteria must the pilot support beyond A4's proposed checks?
- Q7 (S5): Is every field and purpose in A3 necessary, and what retention/deletion periods apply to non-cancelled-event attendance, follows, notifications, and account records?
