# CampusPulse requirements review

Name or team: Nino Matcharashvili

Reviewer: Codex (AI-assisted document review; stakeholder confirmation pending)

Date: 2026-09-08

Review the completed `stakeholders.md` and `REQUIREMENTS.md`. Refer to specific
IDs and evidence in every answer. A yes or no by itself is not enough.

## Validity

Do the requirements represent what the stakeholders need? Which IDs did you
check, and what evidence supports them?

Response: S1's combined discovery and privacy needs appear in UR-1/UR-2,
FR-2/FR-4, and US-1. S2's collaboration, approved publication, audiences, and
corrections map to UR-3–UR-6 and FR-5–FR-9. S3's evidence, hiding, appeals, and
accountability map to UR-7/UR-8/UR-16/UR-17 and FR-11–FR-14. S4/S6 support
verified groups and pilot capacity (FR-7/FR-10, NFR-2); S5 supports minimal
data and the 30-day deadline (FR-15/FR-16, NFR-1). UR-15's date filter is
explicitly a Could proposal under A8, not a request invented for S1. A1–A9
remain proposals for the named stakeholders to confirm.

## Consistency

Do any requirements contradict one another or the release scope?

Response: Section 1 and the Won't list exclude the same six areas; phone-browser
support in UR-11/NFR-3 does not introduce a native app. FR-7/FR-8 prevent
cross-group publication or audience changes. NFR-1/A6 keep the attendance
deletion deadline even during an appeal, resolving stakeholders.md Conflict 1.
Review found that the original FR-9 could disclose time/place changes to a
former member or a recipient of a hidden event, contradicting FR-8/FR-13.
The revision below applies access checks to each notice display while retaining
a generic notification. AC-2.3/AC-2.4, the correction/audience trace rows, A9, and Q5 now
describe the same policy.

## Completeness

Is an important actor, normal flow, failure, permission, privacy rule, or
boundary missing?

Response: The document has 17 URs, 18 FRs, 5 NFRs, 5 stories, and 16 trace rows.
It covers every service named in the first-release brief. Failure and boundary
cases include failed sign-in (FR-1), conflicting draft saves (FR-6), non-member
direct-link access (FR-8), reports without a reason (FR-11), hiding without a
prior report (FR-13), officer restoration attempts (FR-14), and RSVP after
cancellation (FR-16). AC-2.4 adds the missing notification/access boundary. FR-14 and its trace row now include evidence captured by FR-13 when no user report exists. A6/AC-5.2 explicitly include correction-notice attendance links in deletion; NFR-1 scopes inspection to system-controlled copies.
Policies are not all settled: Q3 asks about appeal/evidence retention and
redaction; Q4 asks about officer/membership authority and verification; Q5–Q7
cover notification policy, accessibility coverage, and other data retention.
These questions must be resolved before an agreed implementation baseline.

## Realism

Can the proposed release and its quality targets reasonably be delivered? Mark
unsupported targets as assumptions or open questions.

Response: A browser-only release and the exclusions reduce the delivery scope,
but feasibility cannot be confirmed without staffing and the actual Orientation
Week date (Q1). NFR-2 uses 5,000 students and 200 groups as population counts,
not simultaneous demand. The 100 sessions, 2-second p95, 1% error ceiling,
60-second notice deadline, and workload in A5 are team assumptions awaiting
S4's answer to Q2. A4's assistive configurations and coverage are proposed
checks. NFR-1's 30-day limit comes from S5; deletion from backups and redacted
evidence needs an agreed design with S3/S5 (A6/Q3). The document does not claim
these targets have already been achieved.

## Verifiability

Could a tester decide whether each requirement passes or fails? Identify any
wording that is still vague.

Response: FRs specify observable outcomes: FR-6 rejects a save after another
officer changes the version; FR-8 denies an outsider's direct link; FR-17 has
an exact duplicate comparison and time boundary. Each NFR names a measure,
target, and condition: NFR-1 checks remaining attendance at the 30-day cutoff;
NFR-2 uses the seeded pilot population; NFR-3 names tasks and configurations;
NFR-4 fixes latency/error conditions; NFR-5 times notice availability. Acceptance
criteria have concrete setups and pass/fail results. Structural checks confirmed
that FR/NFR source URs exist and that every trace row has an evidence-to-story
path. Exact supported software versions, actual peak load, and final retention
policies remain release-test-plan inputs under Q2/Q3/Q6/Q7, not verified facts.

## One requirement you revised

- Requirement ID: FR-9.
- Before: FR-9 [Must] The system shall let approved officers correct their own group's event time or place and create an in-service notice for each student with a current RSVP when the correction is saved, showing the old and new values. The notice deadline is NFR-5. [Source: UR-6]
- What was wrong or missing: Every current RSVP recipient received old/new event details even after membership was revoked or the event was hidden. A notice could therefore bypass FR-8/FR-13. The rule also omitted a check when reopening an earlier notice after access changed.
- After: FR-9 [Must] The system shall let approved officers correct their own group's event time or place and create an in-service notice for each student with a current RSVP at successful save time; whenever a notice is displayed, it shall show event identity and old/new values only if the recipient can currently view the event under FR-8 and FR-13, and otherwise show only 'An event you RSVP’d to has changed; details are unavailable' with no event title, group, old/new values, or event link. The notice deadline is NFR-5; the proposed policy is A9. [Source: UR-6, UR-5, UR-16]
- Evidence or stakeholder to confirm the change: S2 requires both audience restrictions and correction notices; S3 requires hiding harmful events. A9 proposes generic notices when access is denied. Confirm this balance with S2/S3/S5. The revised FR-9, US-2 sources, AC-2.3/AC-2.4, the correction/audience trace rows, A9, and Q5 were updated together.

## Final check

- [x] Stakeholder conflicts have a decision or a follow-up question.
- [x] Scope exclusions agree with the Won't list.
- [x] Every FR and NFR traces to a user requirement.
- [x] Every NFR contains a measurable target and condition.
- [x] Traceability rows use IDs that exist in the document.
- [x] The revised requirement has also been updated in the traceability table.
