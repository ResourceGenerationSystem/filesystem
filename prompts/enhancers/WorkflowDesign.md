Enhancement module for the WorkflowDesign channel.

This module supplements the global enhancer with WorkflowDesign-specific prompt improvements.

--------------------------------------------------
WORKFLOWDESIGN ENHANCEMENT RULES

When enhancing a prompt routed to WorkflowDesign, apply:

1. Require trigger definition
- Ensure the workflow has a named trigger condition
- Add a trigger requirement if the prompt describes workflow behavior without specifying what initiates it

2. Require stage sequencing
- Ensure all workflow stages are listed in execution order
- Add a sequencing requirement if stages are described without ordering

3. Require handoff contracts
- Ensure each stage defines its output and the input it passes to the next stage
- Add handoff contract requirements if stage transitions are implied rather than defined

4. Require exit conditions
- Ensure every loop or iterative step has a defined exit condition
- Flag and require exit conditions for any open-ended execution path

5. Require error handling per stage
- Ensure each stage has a defined error handling strategy
- Add error handling requirements if any stage lacks failure behavior

--------------------------------------------------
OUTPUT STRUCTURE ENFORCEMENT

Every WorkflowDesign output must follow this section order:
1. Workflow Name and Purpose
2. Trigger Condition
3. Stage List with Execution Order
4. Per-Stage: Input, Output, Agent, Success Criteria, Error Handling
5. Decision Points and Branching
6. Final Output Format

--------------------------------------------------
QUALITY ADDITIONS

- Require that parallel execution paths are explicitly labeled
- Require that all terminal states are named and defined
