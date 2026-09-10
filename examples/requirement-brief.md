# Requirement Brief — Making an AI Detection Requirement Testable

This is a generalized example based on the kind of requirement and specification review I handled in customer-facing product work.

## Starting point

A draft requirement said the system should return the correct person or vehicle detection result in a timely way.

That sounds clear at first, but it leaves several questions unanswered. If those questions stay open, Engineering can build one interpretation and QA can test another.

## Questions I would raise before calling the requirement ready

### 1. What does “timely” mean?

A requirement should not use words such as “fast” or “timely” unless the expected operating window is defined. The acceptable time may depend on the customer workflow, so the requirement should state the agreed expectation instead of leaving it to interpretation.

### 2. What counts as a correct result?

The requirement should separate the different parts of the result. For example:

- Was a person or vehicle detected?
- Was the object type correct?
- If an attribute such as colour is required, did it match?
- If one part is correct and another is wrong, is the overall result a pass or a failure?

Without this distinction, a technically successful detection can still be wrong for the customer scenario.

### 3. Which scenarios must be tested?

The requirement should include the normal scenario and the important edge cases already seen in real customer use. A feature should not be considered ready only because it passes an ideal test case.

### 4. What happens when the result is uncertain or mismatched?

If the system detects something but the result does not match the expected object or attribute, the requirement should define how that case is handled. It should not be silently counted as success.

## Revised requirement structure

### Problem

Customers need the detection result to match the real operating scenario closely enough for the downstream monitoring workflow to rely on it.

### Expected behaviour

- The system identifies the expected person or vehicle in the defined scenario.
- Required attributes are evaluated separately from the base detection.
- A mismatch is recorded as a mismatch rather than treated as a successful result.
- The result is returned within the operating window agreed for the workflow.

### Acceptance criteria

1. The expected person or vehicle classification matches the test scenario.
2. Any required object or colour attribute is evaluated against the expected result.
3. A required attribute mismatch is treated as a failed or review-needed case, not a pass.
4. UAT includes both normal cases and previously observed customer edge cases.
5. Failed cases are documented and retested after a change.
6. A release recommendation is made only after the relevant previously failing scenarios are retested successfully.

## Why this mattered in practice

The value of the review was not rewriting the requirement to make it longer. It was removing the places where different teams could reasonably interpret the same sentence in different ways.

That made the requirement easier for Engineering to act on, easier for QA to test, and easier to compare against the original customer problem later.

---

This example is generalized from real work and does not reproduce confidential product specifications, customer data, or internal documentation.
