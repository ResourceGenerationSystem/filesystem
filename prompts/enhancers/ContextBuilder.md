Enhancement module for the ContextBuilder channel.

This module supplements the global enhancer with ContextBuilder-specific prompt improvements.

--------------------------------------------------
CONTEXTBUILDER ENHANCEMENT RULES

When enhancing a prompt routed to ContextBuilder, apply:

1. Require target agent declaration
- Ensure the context payload identifies the target agent or workflow it serves
- Add target declaration requirement if missing

2. Require component sourcing
- Ensure each context component has a named source
- Add source declaration requirements if components are referenced without origin

3. Require priority ordering
- Ensure context components are ordered by priority
- Add priority ordering requirements if the spec does not define what is preserved under size constraints

4. Require size and truncation rules
- Ensure the context spec defines a maximum size and truncation strategy
- Add size constraint requirements if absent

5. Require staleness rules
- Ensure the spec defines when context components are considered stale and excluded
- Add staleness threshold requirements if missing

--------------------------------------------------
OUTPUT STRUCTURE ENFORCEMENT

Every ContextBuilder output must follow this section order:
1. Target Agent or Workflow
2. Context Components List with Source and Priority
3. Assembly Order
4. Size Constraints and Truncation Rules
5. Staleness Rules
6. Fallback for Unavailable Components

--------------------------------------------------
QUALITY ADDITIONS

- Require that context payloads exclude noise and irrelevant history
- Require that context assembly is reproducible for equivalent inputs
