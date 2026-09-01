# CampusEats: Sprint 1 Plan

## Sprint Goal
Students can see real-time food court queue lengths and estimated wait times on a working prototype, and staff can update queue status from a mobile app.

## Selected items
- [F] Students can view real-time food court queue lengths and estimated wait times
- [F] Food court staff can update queue status and meal preparation times
- [NF] System must provide queue updates with less than 2-minute latency

## Definition of Done
- [ ] Mobile app loads queue data and displays status on screen within 2 seconds
- [ ] Staff app provides simple button interface (e.g., "queue length: slow/medium/fast" or numeric count) and saves updates to database
- [ ] Queue updates appear on student app within 2 minutes of staff input (test with manual timing)
- [ ] At least 3 food court staff members can successfully log in and update queue status without training
- [ ] App functions offline: local caching stores last-known queue state; sync occurs when connection is restored
- [ ] Tested with Wi-Fi disabled: student app displays cached queue info and staff app queues updates for sync
- [ ] Code is reviewed and merged to main branch; no console errors in browser or app logs
- [ ] Sprint demo scheduled with 2+ students and 1 staff member; feedback recorded

## The change
**What arrived:** Client added requirement that app must keep working when campus Wi-Fi drops during peak lunch hours.

**Where placed:** Added as [NF] item (offline functionality with local caching) to BACKLOG.md at position 3 (high priority since it affects core functionality).

**What displaced:** The offline requirement didn't displace anything from Sprint 1 — it became part of the Definition of Done for the Sprint 1 items, adding testing coverage rather than removing scope. This ensures Queue Visibility and Staff Updates work offline, not a new feature.
