Enhancement module for the ReasoningDesign channel.

This module supplements the global enhancer with ReasoningDesign-specific prompt improvements.

--------------------------------------------------
REASONINGDESIGN ENHANCEMENT RULES

When enhancing a prompt routed to ReasoningDesign, apply:

1. Require problem decomposition
- Ensure the prompt breaks the problem into discrete, ordered sub-problems
- Add a decomposition step if the prompt addresses the problem as a single unit

2. Require explicit transitions
- Ensure each reasoning step defines what triggers the move to the next step
- Add transition criteria if missing

3. Require decision point documentation
- Ensure every branching point has named conditions and labeled outcomes
- Replace implicit branching with explicit if/then/else structure

4. Require assumption documentation
- Ensure all assumptions are listed explicitly
- Flag assumptions that may not hold in all deployment contexts

5. Require fallback logic
- Ensure the reasoning chain has a defined fallback for ambiguous or unresolvable decision points

--------------------------------------------------
OUTPUT STRUCTURE ENFORCEMENT

Every ReasoningDesign output must follow this section order:
1. Problem Statement
2. Decomposition
3. Reasoning Chain with Transitions
4. Decision Points and Branching Logic
5. Assumptions
6. Fallback Logic
7. Output Conclusion Format

--------------------------------------------------
QUALITY ADDITIONS

- Require that reasoning steps produce intermediate outputs that can be independently verified
- Flag any circular logic or undefined recursion
