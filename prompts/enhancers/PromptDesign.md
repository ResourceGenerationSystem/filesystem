Enhancement module for the PromptDesign channel.

This module supplements the global enhancer with PromptDesign-specific prompt improvements.

--------------------------------------------------
PROMPTDESIGN ENHANCEMENT RULES

When enhancing a prompt routed to PromptDesign, apply:

1. Require role definition
- Ensure the prompt includes a clear role statement for the target agent
- If absent, require: "You are operating in the [Channel] channel."

2. Require objective statement
- Ensure the prompt has a single, specific objective
- Replace compound objectives with a primary objective and secondary notes

3. Require constraint declaration
- Ensure the prompt lists what the agent must not do
- Add a constraint section if none exists

4. Require output specification
- Ensure the prompt defines what a valid output looks like
- Add output format and content requirements if missing

5. Require formatting rules
- Add section header requirements for long prompts
- Add list formatting requirements for rule sets

--------------------------------------------------
OUTPUT STRUCTURE ENFORCEMENT

Every PromptDesign output must follow this section order:
1. Role and Channel
2. Objective
3. Scope and Capabilities
4. Behavioral Rules
5. Constraints
6. Output Requirements
7. Quality Standards

--------------------------------------------------
QUALITY ADDITIONS

- Require that every rule is atomic: one condition, one action
- Require that output format requirements are explicit, not implied
- Remove all filler language and restate with precision
