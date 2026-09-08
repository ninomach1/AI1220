# CampusPulse requirements review

Name or team: Nino Matcharashvili

Reviewer: Codex

Date: 2026-09-08

Review the completed `stakeholders.md` and `REQUIREMENTS.md`. Refer to specific
IDs and evidence in every answer. A yes or no by itself is not enough.

## Validity

Do the requirements represent what the stakeholders need? Which IDs did you
check, and what evidence supports them?

Response: S1's discovery need maps to UR-1/FR-2; S5's cancellation deadline maps to UR-13/NFR-1.

## Consistency

Do any requirements contradict one another or the release scope?

Response: Scope and Won't agree. Revised FR-9, AC-2.2, and traceability apply FR-8/FR-13 access rules to notices.

## Completeness

Is an important actor, normal flow, failure, permission, privacy rule, or
boundary missing?

Response: All brief services are covered: 16 URs, 17 FRs, 5 NFRs, 3 stories, and 6 trace rows. Q3–Q7 record unsettled policies.

## Realism

Can the proposed release and its quality targets reasonably be delivered? Mark
unsupported targets as assumptions or open questions.

Response: Deadline/staffing remain Q1; A4/A5 label assumed quality targets. The 5,000 students are a population, not concurrent traffic.

## Verifiability

Could a tester decide whether each requirement passes or fails? Identify any
wording that is still vague.

Response: FR-8 denies unauthorized access; NFR-1 checks deletion at 30 days. A4/A5 define quality checks; software versions remain Q6.

## One requirement you revised

- Requirement ID: FR-9.
- Before: FR-9 [Must] The system shall let approved officers correct their own group's event time or place and create an in-service notice for each student with a current RSVP when the correction is saved, showing the old and new values. The notice deadline is NFR-5. [Source: UR-6]
- What was wrong or missing: Notices could expose event details after access was revoked.
- After: FR-9 [Must] The system shall notify students whose RSVPs are current when approved officers save their group's event time/place changes, within NFR-5. Each notice display shall enforce FR-8/FR-13: show details if access is allowed, otherwise a generic notice without event details or links (A9). [Source: UR-6, UR-5, UR-16]
- Evidence or stakeholder to confirm the change: S2 audience restrictions and S3 hiding; confirm the generic-notice policy with S2/S3/S5.

## Final check

- [x] Stakeholder conflicts have a decision or a follow-up question.
- [x] Scope exclusions agree with the Won't list.
- [x] Every FR and NFR traces to a user requirement.
- [x] Every NFR contains a measurable target and condition.
- [x] Traceability rows use IDs that exist in the document.
- [x] The revised requirement has also been updated in the traceability table.
