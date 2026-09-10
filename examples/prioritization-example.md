# Prioritization Record — Three Competing Issues

I had three issues needing attention at the same time. One was a repeated detection mismatch. Another was an escalation with no named owner. The third was a one-time setup request with a working alternative.

I ordered them by what each issue stopped the customer from doing, whether it had repeated, whether the workaround delivered the required result, what delay would cause, and which team had to act. I did not force those facts into a numerical score. I wrote down why one issue sat above another so the order could be reviewed.

## Issues and decisions

| Issue | Evidence available | Consequence of delay | Current workaround | Decision |
| --- | --- | --- | --- | --- |
| Person or vehicle result does not match the reviewed scene | The same failure had appeared in more than one customer case | Monitoring staff would continue receiving an incorrect result, and the complaint could return | Manually review each case; the returned detection remains wrong | **Priority 1 — Technical review and retest** |
| An escalation moves between teams without one named owner | The response had waited during handoffs because responsibility was not assigned | Resolution would slow, and the customer would wait for an update | A supervisor follows up with each team manually | **Priority 2 — Assign ownership and update the SOP** |
| A one-time setup request already has a working alternative | The request had appeared once, and the current configuration delivered the required outcome | No customer result was blocked | Use the existing configuration | **Priority 3 — Document and revisit only if it repeats** |

## Why the detection issue came first

The detection mismatch affected the result the customer and monitoring team relied on. It had appeared in more than one case, and manual review did not correct the system output. Product, Engineering, and QA needed to review the failure and retest the same case type.

## Why the ownership issue came second

The escalation problem delayed the response, but it did not require a product change. Naming one owner, updating the escalation path, and checking whether handoffs continued addressed the cause without adding an Engineering item.

## Why the one-time request stayed third

The request did not block the required result, had not repeated, and had a working configuration. I kept it documented so the order could change if the workaround stopped working or the request returned.

## Questions I used before setting the order

- What is the customer unable to do?
- Has the same failure appeared more than once?
- Does the workaround deliver the required result, or only make the issue easier to manage?
- What will the customer or operations team experience if the issue waits?
- Does the response need a product change, or can configuration, process, ownership, or communication resolve it?
- Which team must act, and is its dependency available?
- What exact evidence will close the issue?

## Action record

| Priority | Next action | Closure evidence |
| --- | --- | --- |
| 1 | Review the repeated detection mismatch and retest the original case type | The original case and every blocking related case pass the agreed acceptance criteria |
| 2 | Name one escalation owner and update the SOP and handoff path | The escalation begins with one named owner, and the response no longer waits for ownership to be assigned |
| 3 | Record the request and the working configuration | Review the order again only if the request repeats or the configuration stops delivering the required result |

This record combines three recurring situations from my work. I left out customer identifiers, case counts, and internal backlog details.
