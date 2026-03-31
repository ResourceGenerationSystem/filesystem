Agent output schema for the ResourceGenerationSystem.

This file defines the required structure for agent outputs across all channels. Agents must produce outputs that conform to this schema unless a channel-specific schema overrides a field.

--------------------------------------------------
SCHEMA VERSION

Version: 1.0
Applies to: All channel agent outputs

--------------------------------------------------
REQUIRED FIELDS

Every agent output must include the following fields:

1. Channel
Format: plain text, single channel name
Constraint: must be the channel this agent is operating in
Example: SkillBuilder

2. Request summary
Format: one sentence
Constraint: must restate the input request in the agent's own words before producing output
Example: Design a reusable authentication skill for API access.

3. Output type
Format: plain text
Constraint: must declare the type of output being produced
Valid types: specification, plan, schema, analysis, test-plan, safety-spec, workflow, skill-spec, tool-spec, memory-spec, context-spec, prompt, audit-report
Example: skill-spec

4. Output body
Format: structured sections with headers
Constraint: must be self-contained and implementation-ready
Constraint: must not contain unresolved placeholders
Constraint: must apply all applicable enhancement rules

5. Assumptions declared
Format: bulleted list, or "none"
Constraint: any assumption made during generation must be listed explicitly
Example:
- Assumed API uses bearer token authentication
- Assumed retry limit of 3

6. Limitations declared
Format: bulleted list, or "none"
Constraint: any limitation of the output must be stated explicitly
Example:
- Does not cover OAuth2 flows
- Requires external token validation service

--------------------------------------------------
VALID OUTPUT TYPES

specification
plan
schema
analysis
test-plan
safety-spec
workflow
skill-spec
tool-spec
memory-spec
context-spec
prompt
audit-report

--------------------------------------------------
OUTPUT TEMPLATE

Channel: [channel name]
Request summary: [one sentence restatement]
Output type: [output type]

[Output body with structured sections]

Assumptions declared:
- [assumption or none]

Limitations declared:
- [limitation or none]

--------------------------------------------------
VALIDATION RULES

- Channel must match the channel the agent is initialized in
- Output body must not contain placeholders in the form [placeholder]
- Assumptions and limitations must be complete; omission is not acceptable when assumptions or limitations exist
- Output type must match one of the valid types listed above
- Output body must be structured with section headers for responses longer than three paragraphs
