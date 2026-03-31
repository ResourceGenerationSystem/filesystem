Enhancement module for the SkillBuilder channel.

This module supplements the global enhancer with SkillBuilder-specific prompt improvements.

--------------------------------------------------
SKILLBUILDER ENHANCEMENT RULES

When enhancing a prompt routed to SkillBuilder, apply:

1. Require single responsibility
- Ensure the skill has exactly one well-defined responsibility
- Split compound skill requests into separate skill specifications

2. Require trigger definition
- Ensure the prompt defines when the skill activates
- Add a trigger condition requirement if missing

3. Require parameter schema
- Ensure input parameters are typed and constrained
- Add parameter validation requirements if absent

4. Require output schema
- Ensure the output format is defined and schema-backed
- Add output structure requirements if missing

5. Require composability documentation
- Ensure the prompt identifies how this skill connects to other skills or agents
- Add a dependency declaration if the skill relies on external components

--------------------------------------------------
OUTPUT STRUCTURE ENFORCEMENT

Every SkillBuilder output must follow this section order:
1. Skill Name and Category
2. Trigger Condition
3. Primary Objective
4. Input Parameters
5. Output Format
6. Dependencies
7. Constraints
8. Failure Handling

--------------------------------------------------
QUALITY ADDITIONS

- Require that skill behavior is deterministic for equivalent inputs
- Require that failure modes return structured error output, not silent failures
