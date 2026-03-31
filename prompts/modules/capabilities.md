Capabilities module for the ResourceGenerationSystem.

This module defines how agent capabilities must be declared, scoped, and referenced across the system.

--------------------------------------------------
PURPOSE

This module provides a canonical definition of how capabilities are declared, what makes a capability valid, and how capabilities are used in agent specs, configs, and routing logic.

--------------------------------------------------
CAPABILITY DECLARATION FORMAT

Every capability must be declared with the following fields:

Name:
[Unique lowercase hyphenated identifier for the capability]

Description:
[One sentence describing what the agent can do with this capability]

Inputs:
[What this capability requires to execute]

Outputs:
[What this capability produces]

Constraints:
[What this capability cannot do or is limited by]

--------------------------------------------------
CANONICAL CAPABILITY CATEGORIES

routing
Description: Receives, classifies, and dispatches requests to the appropriate channel.
Applies to: master-router

prompt-enhancement
Description: Improves prompt quality, structure, and completeness before routing or execution.
Applies to: master-router, prompt-design

agent-scaffolding
Description: Defines the structure, identity, and configuration of a new agent.
Applies to: agent-builder

agent-configuration
Description: Applies settings and parameters to initialize an agent for deployment.
Applies to: agent-builder

prompt-authoring
Description: Creates new prompts with defined role, objective, constraints, and output format.
Applies to: prompt-design

prompt-optimization
Description: Improves existing prompts for clarity, precision, and execution quality.
Applies to: prompt-design

chain-of-thought
Description: Constructs step-by-step reasoning chains for complex multi-step problems.
Applies to: reasoning-design

logical-decomposition
Description: Breaks a problem into discrete, ordered, and independently verifiable sub-problems.
Applies to: reasoning-design

skill-composition
Description: Combines multiple skill modules into a composite capability without conflict.
Applies to: skill-builder

skill-validation
Description: Verifies that a skill module meets interface and behavioral contracts.
Applies to: skill-builder

tool-creation
Description: Defines the interface, behavior, and integration contract for a new tool.
Applies to: tool-builder

api-integration
Description: Specifies how an agent connects to and interacts with an external API.
Applies to: tool-builder

workflow-creation
Description: Designs a multi-stage execution plan with ordered steps and handoff contracts.
Applies to: workflow-design

step-sequencing
Description: Defines the execution order and dependencies between workflow stages.
Applies to: workflow-design

memory-schema-design
Description: Specifies the structure, scope, and lifecycle of an agent memory store.
Applies to: memory-design

memory-retrieval
Description: Defines how and when stored memory is accessed and surfaced.
Applies to: memory-design

context-assembly
Description: Constructs a context payload from defined sources for agent invocation.
Applies to: context-builder

context-pruning
Description: Removes irrelevant, stale, or oversized content from a context payload.
Applies to: context-builder

test-case-specification
Description: Defines exact inputs, expected outputs, and pass/fail criteria for a test.
Applies to: testing-design

failure-mode-analysis
Description: Identifies and documents failure modes with corresponding test coverage.
Applies to: testing-design

safety-rule-design
Description: Defines behavioral constraints that prevent unsafe or out-of-scope outputs.
Applies to: safety-design

guardrail-specification
Description: Specifies enforcement points and response logic for safety rule violations.
Applies to: safety-design

--------------------------------------------------
USAGE RULES

- Capabilities must be declared in agent config.json under the "capabilities" array
- Capability names must match the canonical identifiers listed in this module
- New capabilities require a full declaration before use; undeclared capabilities are not valid
- Capabilities must not overlap in responsibility without explicit composition documentation
- Capabilities must be independently testable
