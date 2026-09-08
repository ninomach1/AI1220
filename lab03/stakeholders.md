# CampusPulse stakeholder analysis

Name or team: Nino Matcharashvili

Date: 2026-09-08

Read the stakeholder notes in the lab handout before completing this file.
Use the stakeholder types and power-interest quadrants from Week 2, Lecture 2.

Stakeholder types: end user, operations, business, regulator, negative stakeholder

Power-interest quadrants: key player, keep satisfied, keep informed, minimal effort

## S1

- Stakeholder: Student attendee.
- Stakeholder type: End user.
- Power-interest quadrant: Keep informed (low power, high interest). Individual students have limited authority over the project but use its services directly.
- Main goal: Follow several clubs and find their events and announcements in one place, including from a phone.
- Main concern: RSVP participation must not become public without the student's choice, and students using screen readers must be able to use the service.
- How you would involve or monitor this stakeholder: Invite students, including screen-reader users, to review mobile-browser prototypes and try following, event discovery, and RSVP tasks. Ask them to check whether privacy choices are clear and gather feedback during the pilot.

## S2

- Stakeholder: Group officer.
- Stakeholder type: End user.
- Power-interest quadrant: Keep informed (low power, high interest). Officers control their group's content but are not described as having authority over platform policy or the release scope.
- Main goal: Collaborate on announcements, publish through approved officers, and communicate events to the intended audience.
- Main concern: Unapproved people must not publish; members-only events must respect their audience boundary; students who RSVP must receive changes to the time or place.
- How you would involve or monitor this stakeholder: Ask officers from several groups to review shared drafting and publishing workflows. Walk through approval, university-wide versus members-only visibility, and an event correction that must reach students who RSVP'd.

## S3

- Stakeholder: Campus moderator.
- Stakeholder type: Operations.
- Power-interest quadrant: Key player (high power, high interest). Moderators can directly affect event visibility and depend on the reporting and moderation tools to do their work.
- Main goal: Review reports and hide harmful events immediately when necessary while supporting appeals.
- Main concern: Reports must preserve the reported content and reason, evidence must remain available for appeals, and each decision must identify who made it.
- How you would involve or monitor this stakeholder: Work closely with moderators to define report details, hiding permissions, evidence access, and decision records. Review scenarios covering urgent removal, an appeal, and access to the original evidence after an event is hidden.

## S4

- Stakeholder: Student Affairs.
- Stakeholder type: Business.
- Power-interest quadrant: Key player (high power, high interest). As the service sponsor, Student Affairs is assumed to influence release priorities and acceptance of the pilot.
- Main goal: Launch a trustworthy pilot for 5,000 students and 200 groups before Orientation Week.
- Main concern: An official badge must only identify a group that has actually been checked, and the pilot must be ready for its intended users by the deadline.
- How you would involve or monitor this stakeholder: Hold regular scope and readiness reviews, agree on the group-verification process, and confirm the actual Orientation Week deadline. Ask for expected peak concurrent usage because the pilot population alone does not establish peak traffic.

## S5

- Stakeholder: Data Protection Officer.
- Stakeholder type: Regulator (the project's privacy oversight role).
- Power-interest quadrant: Key player (high power, high interest). Privacy oversight is assumed to constrain data-handling decisions, and the source explicitly identifies privacy and retention needs for this service.
- Main goal: Limit personal-data collection to what CampusPulse needs and protect attendance information.
- Main concern: RSVP lists must start private, and attendance data for a cancelled event must be deleted within 30 days; moderation evidence must not become a reason to retain unnecessary personal data.
- How you would involve or monitor this stakeholder: Review the proposed personal-data fields, RSVP defaults, access rules, and deletion process with the officer. Resolve the boundary between attendance data and appeal evidence together with campus moderators.

## S6

- Stakeholder: People impersonating verified groups or abusing compromised group accounts.
- Stakeholder type: Negative stakeholder.
- Power-interest quadrant: Key player (high potential power, high interest in abuse). They have no legitimate decision-making authority, but successful phishing or repeated posting could disrupt the pilot and damage trust.
- Main goal: From the attacker's perspective, impersonate a trusted group to publish phishing content or use a compromised account to post the same announcement repeatedly.
- Main concern: From the attacker's perspective, being detected and losing the ability to publish. For the project, the concern is students being deceived and announcements being flooded with repeated posts.
- How you would involve or monitor this stakeholder: Monitor impersonation reports and repeated posting, and use controlled abuse scenarios to review verification and moderation controls. Treat the quadrant as a reason for close monitoring, not an invitation to involve attackers in project decisions.

## Conflicts to resolve

Describe at least two real tensions. For each one, name both stakeholder IDs
and either propose a decision or write a specific question that should go back
to the stakeholders.

### Conflict 1

- Stakeholders: S3 (Campus moderator) and S5 (Data Protection Officer).
- What conflicts: Moderators need evidence for an appeal, while the Data Protection Officer requires minimal personal-data collection and deletion of cancelled-event attendance data within 30 days. Keeping an entire event record for an appeal could also retain attendance data beyond that deadline.
- Proposed decision or follow-up question: Proposed decision: keep reported-content evidence and moderation decisions separate from attendance lists, and continue to delete cancelled-event attendance data within 30 days. Ask S3 and S5: "Which fields are essential for an appeal, how should attendance information embedded in evidence be removed, and how long should the remaining report and decision records be retained?" No exception to the attendance-deletion deadline is assumed.

### Conflict 2

- Stakeholders: S2 (Group officer) and S3 (Campus moderator).
- What conflicts: Officers use published events to reach their chosen audience and communicate corrections, while moderators may need to hide an event immediately. Hiding interrupts the group's communication even before an appeal establishes whether the decision should stand.
- Proposed decision or follow-up question: Proposed decision: allow moderators to hide a reported event immediately, record the reason and the decision-maker, and preserve the reported evidence for review. Notify the group's approved officers of the decision and provide an appeal route. Officers must not be able to restore the hidden event themselves; restoration requires a recorded moderation decision. Confirm this proposed workflow with officers and moderators.
