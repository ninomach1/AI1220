# CampusPulse requirements review

Name or team: Nino Matcharashvili

Reviewer: Codex

Date: 2026-09-08

Review the completed `stakeholders.md` and `REQUIREMENTS.md`. Refer to specific
IDs and evidence in every answer. A yes or no by itself is not enough.

## Validity

Do the requirements represent what the stakeholders need? Which IDs did you
check, and what evidence supports them?

Response: S1’s discovery need maps to UR-1/FR-2; S2’s corrections map to UR-6/FR-9. S5’s 30-day deletion request maps to UR-13/FR-16/NFR-1.

## Consistency

Do any requirements contradict one another or the release scope?

Response: Section 1 and Won’t exclude the same six areas. Revised FR-9 enforces FR-8/FR-13 when displaying notices; AC-2.4 and A9 reflect this access rule.

## Completeness

Is an important actor, normal flow, failure, permission, privacy rule, or
boundary missing?

Response: The document contains 17 URs, 18 FRs, 5 NFRs, 5 stories, and 16 trace rows. FR-1/FR-8/FR-13/FR-16 cover authentication, access, hiding, and cancellation boundaries; Q3–Q7 identify unresolved policies.

## Realism

Can the proposed release and its quality targets reasonably be delivered? Mark
unsupported targets as assumptions or open questions.

Response: Browser-only scope reduces delivery work, but staffing and the deadline remain unconfirmed (Q1). A4/A5 mark proposed accessibility/performance targets; Q2/Q3 require workload and retention decisions.

## Verifiability

Could a tester decide whether each requirement passes or fails? Identify any
wording that is still vague.

Response: FR-6 rejects stale saves, FR-8 denies unauthorized links, and NFR-1 requires zero attendance records at 30 days. Q2/Q3/Q6/Q7 leave load, software versions, and retention details open.

## One requirement you revised

- Requirement ID: FR-9.
- Before: FR-9 [Must] The system shall let approved officers correct their own group's event time or place and create an in-service notice for each student with a current RSVP when the correction is saved, showing the old and new values. The notice deadline is NFR-5. [Source: UR-6]
- What was wrong or missing: Notices could expose restricted event details after access changed. FR-9 lacked a check when reopening notices.
- After: FR-9 [Must] The system shall create correction notices for students whose RSVPs are current when an approved officer saves a change to their group's event time or place. Each notice display shall recheck FR-8/FR-13: authorized recipients see old/new details; others see only a generic change notice without event title, group, values, or link (A9). Notices meet NFR-5. [Source: UR-6, UR-5, UR-16]
- Evidence or stakeholder to confirm the change: S2’s audience restrictions and S3’s hiding rule require notice access checks. FR-9, AC-2.4, traceability, and A9/Q5 align; S2/S3/S5 confirmation remains pending.

## Final check

- [x] Stakeholder conflicts have a decision or a follow-up question.
- [x] Scope exclusions agree with the Won't list.
- [x] Every FR and NFR traces to a user requirement.
- [x] Every NFR contains a measurable target and condition.
- [x] Traceability rows use IDs that exist in the document.
- [x] The revised requirement has also been updated in the traceability table.
