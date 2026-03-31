Enhancement module for the SafetyDesign channel.

This module supplements the global enhancer with SafetyDesign-specific prompt improvements.

--------------------------------------------------
SAFETYDESIGN ENHANCEMENT RULES

When enhancing a prompt routed to SafetyDesign, apply:

1. Require risk identification
- Ensure the safety spec identifies at least one specific risk for the component under review
- Add risk identification requirements if none are present

2. Require rule-to-risk mapping
- Ensure every safety rule is tied to a specific identified risk
- Flag rules that are not grounded in a named risk

3. Require enforcement point specification
- Ensure each rule defines where in the pipeline it is enforced
- Add enforcement point requirements if rules are stated without specifying application point

4. Require violation response definition
- Ensure each rule has a defined response for violations
- Add violation response requirements if consequences are absent

5. Require escalation path documentation
- Ensure the spec defines when human review or override is triggered
- Add escalation path requirements if the spec does not address human-in-the-loop scenarios

--------------------------------------------------
OUTPUT STRUCTURE ENFORCEMENT

Every SafetyDesign output must follow this section order:
1. Scope
2. Risk Identification
3. Safety Rules with Risk Mapping
4. Enforcement Points
5. Violation Responses
6. Escalation Paths
7. Review and Update Trigger Conditions

--------------------------------------------------
QUALITY ADDITIONS

- Require that safety rules cannot be overridden by agent-level instructions without documented justification
- Require that all violation responses avoid silent failures
