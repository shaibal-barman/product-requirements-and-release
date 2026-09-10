# Requirement Brief — Making an AI Detection Requirement Testable

I reviewed a draft AI-detection requirement that used “correct” and “timely” without defining either term. Engineering had no single build target, and QA had no pass/fail rule. I raised the following questions before development and release review.

## Starting point

The draft asked the system to return the correct person or vehicle detection result in a timely way.

It did not define the object and attribute rules, timing target, treatment of mismatches, or cases QA needed to test.

## Questions I raised

### 1. What exact time limit applies?

The specification needed four details:

- the maximum allowed response time;
- the event that starts the clock;
- the event that stops the clock;
- the pass/fail rule when the limit is missed.

I have left out the internal timing target. In the working specification, the field needed a number and unit—not “fast” or “timely.”

### 2. What makes the result correct?

I separated the result into three decisions:

- **Base classification:** Did the system identify the expected person or vehicle?
- **Required attribute:** If colour or another attribute was in scope, did it match the reviewed scene?
- **Case status:** If either required result was wrong, did the case fail or move to manual review?

Without separate rules, a detected vehicle with the wrong colour could be counted as correct even though the returned result did not match the customer’s case.

### 3. Which cases must QA test?

The test set needed:

- the normal customer scenario;
- every previously failing customer scenario included in the release;
- a case where the base classification was correct but a required attribute was wrong;
- a case where the system could not return a reliable match.

Each case needed its expected output before testing began.

### 4. How should a mismatch be recorded?

The requirement had to state whether a mismatch was a failure, a manual-review result, or no reliable result. A mismatch could not be counted as a pass.

## Rewritten requirement

### Problem

Monitoring staff use the detection result to interpret a camera event. If the returned object type or required attribute does not match the reviewed scene, they cannot rely on that result when deciding how to respond.

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
7. Every blocking case passes before the change receives a release-ready recommendation. Each remaining limitation records its effect and owner.

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

Before I clarified the wording, Engineering and QA could agree that the result should be “correct” and “timely” but still use different pass criteria. Defining each field gave Engineering a target and gave QA a recorded rule for pass, fail, and retest.

I rebuilt this brief without customer or product names. The internal timing target, test media, and employer documents are not included.
