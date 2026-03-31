Failure handling module for the ResourceGenerationSystem.

This module defines how failures must be identified, categorized, responded to, and reported across all channels and agents.

--------------------------------------------------
PURPOSE

This module provides canonical failure handling rules for all agents and workflows in the system. Every agent must implement these rules unless a channel-specific override is explicitly documented.

--------------------------------------------------
FAILURE CATEGORIES

1. INPUT FAILURE
Condition: the input is missing, malformed, incomplete, or does not conform to the expected schema.
Required response: reject the input, return a structured error with the failure reason, and do not proceed with processing.
Silent failure: not permitted.

2. COMMAND FAILURE
Condition: a command is provided but does not match the expected format or references an unknown target.
Required response: return the defined help block for the channel. Do not attempt to interpret the command.
Silent failure: not permitted.

3. SOURCE FAILURE
Condition: a required source module, template, schema, or config cannot be retrieved.
Required response: if the source is required, halt and report the missing source. If the source is optional, continue with documented fallback behavior and note the gap explicitly in output.
Silent failure: not permitted.

4. ROUTING FAILURE
Condition: the MasterRouter cannot determine a valid primary channel for a request.
Required response: default to AgentBuilder for agent-related requests, PromptDesign for unclassifiable prompt requests. Document the routing ambiguity in the routing rationale field.
Silent failure: not permitted.

5. EXECUTION FAILURE
Condition: an agent begins processing a valid request but cannot produce a complete, valid output.
Required response: return whatever partial output is available, clearly marked as incomplete, along with the reason execution could not be completed. Do not return empty output.
Silent failure: not permitted.

6. VALIDATION FAILURE
Condition: an output is generated but fails schema validation or quality checks.
Required response: report the validation failure with the specific field or rule that failed. Do not return the invalid output as complete.
Silent failure: not permitted.

7. ESCALATION TRIGGER
Condition: a failure is ambiguous, repeating, or involves a safety or security concern.
Required response: halt execution, document the trigger condition, and flag for human review. Do not attempt automated resolution of safety-related failures.

--------------------------------------------------
FAILURE RESPONSE FORMAT

Every failure response must include:

Failure type: [category from the list above]
Condition: [specific condition that triggered the failure]
Agent: [name of the agent that encountered the failure]
Input summary: [brief description of the input that caused the failure]
Response: [exact action taken]
Recovery path: [what the caller should do next, if applicable]

--------------------------------------------------
HARD RULES

- No agent may return empty output on failure
- No agent may proceed silently on a known failure condition
- Every failure type must have a corresponding test case in the testing-design channel
- Failure responses must conform to the agent-output schema
- Safety-related failures must always escalate; they must not be suppressed or auto-resolved
