# CampusEats: Process Plan and Milestones

## Process Decision

### How much do we know now about what is needed?
We have a clear problem statement (long queues at food court) and initial scope (queue visibility, pre-ordering). However, we don't know the exact business model, pricing structure, whether orders go to one kitchen or multiple vendors, or integration requirements with existing payment systems.

### How much can change after we start?
Significant change is likely. Student needs for queue prediction may differ from staff needs. Food court operations and staffing availability may constrain what's feasible. Vendor participation could expand or shrink the feature set.

### How often can we get feedback from users?
We have direct access to students and food court staff daily, so feedback can come every day or every sprint if we ask for it.

### How critical is predictability of schedule and budget?
The lab operates on a fixed timeline (one semester), but this is an exploratory student project. Business criticality is low compared to production systems.

### Verdict:
**Iterative/Agile with short sprints.** Clear initial scope but high uncertainty about details, good user access for rapid feedback, and low business risk make incremental development ideal.

---

## Milestones

| Date | Milestone | How to Check |
|------|-----------|--------------|
| End of Sprint 1 (2 weeks) | Queue visibility prototype working on campus | Staff can see live queue counts from mobile app; students report accurate wait times displayed |
| End of Sprint 2 (4 weeks) | Pre-ordering MVP deployed to pilot group | 20 students successfully pre-order and pick up meals; staff reports no major operational disruption |
| End of Sprint 3 (6 weeks) | Payment integration complete and tested | Students pay via existing campus card; no failed transactions in first 50 orders |

## Risks

| Risk | Likelihood | Impact | Mitigation |
|------|------------|--------|-----------|
| Food court staff resistant to reporting queue status manually | Medium | High | Meet with staff in Sprint 1; offer mobile app that auto-detects queue size via camera/sensors if manual input fails |
| Multiple vendor systems don't integrate | High | High | In Sprint 1, interview each vendor's IT; pick integration method (API, webhook, polling) before implementation |
| Pre-orders cause bottlenecks if kitchen can't fulfill volume | Medium | High | Cap pre-order volume in Sprint 1; add queue prediction to prevent overwhelming kitchen capacity |
