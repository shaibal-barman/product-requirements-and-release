# Prioritization Example — Deciding What Needs Attention First

This is a generalized example of how I compared product and service issues when several things needed attention at the same time.

I did not use a score just to make the decision look precise. I looked at the customer consequence, how often the issue was happening, whether there was a workable alternative, and what would happen if we delayed it.

## Three issues under review

| Issue | Customer impact | Recurrence | Workaround | Operational consequence | Priority |
| --- | --- | --- | --- | --- | --- |
| Person or vehicle detection is wrong in repeated customer scenarios | High | Repeated | Limited | Can affect the monitoring outcome and create repeat complaints | **1 — Fix first** |
| Ownership is unclear during a recurring service escalation | Medium to high | Repeated | Manual follow-up | Slows resolution and creates unnecessary handoffs | **2 — Address next** |
| A one-off request can be handled with the current setup | Low | Isolated | Available | Little immediate effect on service delivery | **3 — Schedule later** |

## Why the first issue moved ahead

The detection problem affected the result the customer was depending on. It was not an isolated preference, and the available workaround was limited. Leaving it unresolved also meant the same type of issue could keep returning through support and operations.

That combination made it more important than a request that was inconvenient but still had a usable workaround.

## Why the second issue still mattered

An ownership problem may not require a product change, but repeated confusion during escalation still affects the customer experience. In this case, the better response could be a clearer SOP, escalation path, or responsibility split rather than engineering work.

The important part was not forcing every recurring problem into the product backlog.

## What I checked before changing the order

- How many customers or workflows were affected?
- Was the issue recurring or isolated?
- Did it block the expected customer outcome?
- Was there a reliable workaround?
- Would delaying it create more support or operational effort?
- Did another team or dependency need to be ready first?
- Was the proposed response actually a product change, or would a service/process fix solve it better?

## Decision record

**Priority 1:** Repeated detection issue — move into technical review and retest against the original customer scenarios.

**Priority 2:** Recurring escalation ownership issue — clarify the operating process and track whether repeat resolution time improves.

**Priority 3:** One-off request with a workable alternative — keep documented and schedule only if the need becomes more important or more common.

---

This example is based on recurring patterns from real work. The issue wording and details are generalized so no confidential customer or internal information is exposed.
