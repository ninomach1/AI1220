# Backlog — StudyMatch

StudyMatch helps first-year students find compatible classmates and arrange productive study sessions.

## Items

- [F] First-year students are matched only with students from their own college during their first semester.
- [F] First-year students can find study partners who are taking the same course.
- [F] Students can compare potential partners' study goals and availability with their own.
- [F] Students can arrange and confirm a study session with matched partners.
- [NF] Students' contact details and schedules are visible only to people they explicitly approve.
- [F] Students can block another person so they do not appear in each other's future matches. (assistant)
- [F] Students can leave or report a match that feels unsafe or inappropriate.
- [F] Students can update their courses, study preferences, and availability.
- [NF] Matching results appear within two seconds for at least 95% of requests with 1,000 concurrent users.
- [NF] StudyMatch is available at least 99.5% of the time between 07:00 and 23:00 during teaching weeks. (assistant)
- [NF] Core matching and session-planning tasks are usable with keyboard navigation and screen readers.

## The change

The Dean's office made same-college matching mandatory for first-year students during their first semester. I placed this item first because it is an immediate, non-negotiable eligibility rule that every match must satisfy. It entered Sprint 1 and displaced the study-session arrangement item, keeping the sprint at three items; compliant matching must work before session planning adds value.

## From the assistant

Prompt used: "For StudyMatch, suggest exactly five additional backlog items. Return each as one need on one line beginning with `- [F]` or `- [NF]`; describe what users or operators need, not a technology or implementation."

Kept:

- [F] Students can block another person so they do not appear in each other's future matches. — Kept because it closes an important safety gap after an unwanted interaction.
- [NF] StudyMatch is available at least 99.5% of the time between 07:00 and 23:00 during teaching weeks. — Kept because students need dependable access around varied class schedules.

Rejected:

- [F] Students receive a reminder before a confirmed study session. — Rejected because reminders add little value until core session planning is validated.
- [F] Students can publish ratings of study partners after sessions. — Rejected because public ratings introduce bias and retaliation risks not justified by the brief.
- [F] Students earn badges for completed study sessions. — Rejected because there is no evidence that gamification addresses the study-partner matching problem.
