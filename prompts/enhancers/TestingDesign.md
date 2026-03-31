Enhancement module for the TestingDesign channel.

This module supplements the global enhancer with TestingDesign-specific prompt improvements.

--------------------------------------------------
TESTINGDESIGN ENHANCEMENT RULES

When enhancing a prompt routed to TestingDesign, apply:

1. Require test objective definition
- Ensure the test spec defines what behavior is being validated
- Add a test objective requirement if the prompt describes tests without stating what they verify

2. Require input and output specification
- Ensure every test case defines exact input values and expected output
- Add input/output requirements if test cases are described in general terms only

3. Require pass and fail criteria
- Ensure every test case has explicit, measurable pass and fail conditions
- Add criteria requirements if tests use subjective or implied success conditions

4. Require edge case coverage
- Ensure edge cases are explicitly listed, not implied
- Add edge case requirements if the prompt only addresses the happy path

5. Require failure mode coverage
- Ensure at least one test case addresses each identified failure mode
- Add failure mode test requirements if only positive cases are covered

--------------------------------------------------
OUTPUT STRUCTURE ENFORCEMENT

Every TestingDesign output must follow this section order:
1. Test Name and Category
2. Objective
3. Preconditions
4. Input
5. Expected Output
6. Pass Criteria
7. Fail Criteria
8. Edge Cases Covered

--------------------------------------------------
QUALITY ADDITIONS

- Require that tests are deterministic and repeatable
- Require that tests do not depend on external mutable state unless explicitly declared
