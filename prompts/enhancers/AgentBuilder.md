Enhancement module for the AgentBuilder channel.

This module supplements the global enhancer with AgentBuilder-specific prompt improvements.

--------------------------------------------------
AGENTBUILDER ENHANCEMENT RULES

When enhancing a prompt routed to AgentBuilder, apply:

1. Require agent identity definition
- Ensure the prompt specifies a clear agent name and assigned channel
- If missing, flag and add a placeholder with instructions to fill it in

2. Require capability scope
- Ensure the prompt defines what the agent can and cannot do
- Add explicit capability boundaries if absent

3. Require interface contracts
- Ensure input schema and output schema are defined
- Add schema structure requirements if missing

4. Require behavioral rules
- Ensure the prompt includes at least one behavioral constraint
- Add a requirement for fallback behavior definition

5. Require dependency declaration
- Ensure all tools, models, and external dependencies are named explicitly

--------------------------------------------------
OUTPUT STRUCTURE ENFORCEMENT

Every AgentBuilder output must follow this section order:
1. Agent Name and Channel
2. Primary Objective
3. Capabilities and Scope
4. Input Schema
5. Output Schema
6. Behavioral Rules and Constraints
7. Dependencies
8. Fallback and Error Handling

--------------------------------------------------
QUALITY ADDITIONS

- Add a requirement that the spec is deployable without additional context
- Add a requirement that all behavioral rules use conditional language: "if X then Y"
