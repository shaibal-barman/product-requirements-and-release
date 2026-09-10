# Requirement Brief — Making an AI Detection Requirement Testable

A draft AI-detection requirement used two words that sounded specific—“correct” and “timely”—but neither gave Engineering a build target or QA a pass/fail rule. The questions below show how I removed that ambiguity before development and release review.

## Starting point

The draft effectively asked the system to return the correct person or vehicle detection result in a timely way.

That wording did not define the object and attribute rules, timing target, treatment of mismatches, or cases QA needed to test.

## Questions I raised

### 1. What exact time limit applies?

The specification needed four details:

- the maximum allowed response time;
- the event that starts the clock;
- the event that stops the clock;
- the pass/fail rule when the limit is missed.

The internal timing target is not published here. In an active requirement, this field must contain a number and unit—not “fast” or “timely.”

### 2. What makes the result correct?

I separated the result into three decisions:

- **Base classification:** Does the result identify the expected person or vehicle?
- **Required attribute:** If colour or another attribute is in scope, does it match the reviewed scene?
- **Case status:** If either required result is wrong, does the case fail or move to manual review?

Without separate rules, a detected vehicle with the wrong colour could be counted as correct even though the returned result did not match the customer’s case.

### 3. Which cases must QA test?

The test set needed:

- the normal customer scenario;
- every previously failing customer scenario included in the release;
- a case where the base classification is correct but a required attribute is wrong;
- a case where the system cannot return a reliable match.

Each case needed its expected output before testing began.

### 4. How should a mismatch be recorded?

The requirement had to state whether a mismatch was a failure, a manual-review result, or no reliable result. A mismatch could not be counted as a pass.

## Rewritten requirement

### Problem

Monitoring staff use detection output to interpret a camera event. If the returned object type or required attribute does not match the reviewed scene, the output cannot support the intended monitoring decision.

### Expected behaviour

- Each approved test case has a known person or vehicle classification.
- Each required attribute has a separate expected value.
- The system returns the base classification and required attribute within the documented time limit.
- A base-classification or required-attribute mismatch is recorded as a failure.
- The test record keeps the expected and observed results separate.

### Acceptance criteria

1. The expected base classification is recorded before the test starts.
2. The returned person or vehicle classification matches the expected classification.
3. Each required attribute matches the expected value.
4. A base-classification or required-attribute mismatch receives a failed status.
5. The UAT set includes the normal case and every blocking customer case that failed before the change.
6. Every failed case records the case ID, expected result, observed result, and retest result.
7. A release-readiness recommendation is given only after every blocking case passes. Any remaining limitation is listed with its effect and owner.

## Evidence required in the review

| Field | Required entry |
| --- | --- |
| Test case ID | One traceable ID for the case |
| Source | Customer report, approved replay, or recreated scenario |
| Expected result | Base classification, required attribute, and time limit |
| Observed result | The exact result returned during the test |
| Status | Pass or fail with the reason |
| Retest | Build or version tested, date, and result |
| Owner | Person or team responsible for an unresolved failure |

## Why the review mattered

Before clarification, Engineering and QA could agree that the result should be “correct” and “timely” but still use different pass criteria. Defining each field gave Engineering a target and gave QA a recorded rule for pass, fail, and retest.

This file reconstructs the structure of the review. Customer names, product names, the internal timing target, test media, and employer documents are not included.
