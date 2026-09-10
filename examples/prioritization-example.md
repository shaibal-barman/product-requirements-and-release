# Prioritization Record — Three Competing Issues

A repeated detection problem, an escalation-ownership gap, and a one-time setup request were competing for attention. I compared them by the customer result at risk, recurrence, available workaround, consequence of delay, and team dependency.

I did not add a numerical score that implied more certainty than the evidence supported. I recorded the reason for the order so another person could challenge or approve it.

## Issues and decisions

| Issue | Evidence available | Consequence of delay | Current workaround | Decision |
| --- | --- | --- | --- | --- |
| Person or vehicle result does not match the reviewed scene | The same failure pattern appears in more than one customer case | Monitoring staff continue receiving an incorrect result, and the complaint can return | Manually review each case; the returned detection remains wrong | **Priority 1 — Technical review and retest** |
| An escalation moves between teams without one named owner | The response waits during handoffs because responsibility is not assigned | Resolution slows and the customer waits for an update | A supervisor follows up with each team manually | **Priority 2 — Assign ownership and update the SOP** |
| A one-time setup request already has a working alternative | The request has appeared once, and the current configuration delivers the required outcome | No customer outcome is blocked | Use the existing configuration | **Priority 3 — Document and revisit only if it repeats** |

## Why the detection issue came first

The detection mismatch affected the result the customer and monitoring team relied on. It had appeared in more than one case, and manual review did not correct the system output. The next action needed Product, Engineering, and QA to review the failure and retest the same case type.

## Why the ownership issue came second

The escalation problem delayed the response, but it did not require a product change. Naming one owner, updating the escalation path, and checking whether handoffs continued addressed the cause without adding an Engineering item.

## Why the one-time request stayed third

The request did not block the required outcome, had not repeated, and had a working configuration. I kept it documented so the decision could change if the workaround stopped working or the request returned.

## Questions I used before setting the order

- Which required customer result is blocked?
- Has the same failure appeared in more than one case?
- Does the workaround fully deliver the required result, or only reduce the immediate effect?
- What will the customer or operations team experience if the issue waits?
- Does the response require a product change, or can configuration, process, ownership, or communication resolve it?
- Which team or dependency must be available before work can start?
- What evidence will show that the issue is closed?

## Action record

| Priority | Next action | Closure evidence |
| --- | --- | --- |
| 1 | Review the repeated detection mismatch and retest the original case type | The original case and every blocking related case pass the agreed acceptance criteria |
| 2 | Name one escalation owner and update the SOP and handoff path | The response no longer waits for ownership to be assigned |
| 3 | Record the request and the working configuration | Reassess only if the request repeats or the configuration stops delivering the required result |

The three rows combine recurring situations I handled. Customer identifiers, case counts, and internal backlog details are omitted.
