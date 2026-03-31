Safety blocks module for the ResourceGenerationSystem.

This module defines the canonical safety blocks that must be applied by agents across channels. Safety blocks are non-negotiable constraints that cannot be overridden by agent-level instructions.

--------------------------------------------------
PURPOSE

This module provides a reusable set of safety constraints for inclusion in agent specs, install prompts, and workflow definitions. These blocks apply universally unless a channel-specific exemption is explicitly documented and reviewed.

--------------------------------------------------
SAFETY BLOCK DEFINITIONS

--------------------------------------------------
BLOCK: NO SILENT FAILURE

Rule: an agent must never return empty output, null output, or an unchanged input as its response to a failure condition.
Enforcement point: output validation, before response is returned to caller.
Violation response: the failure must be named, the failure type declared, and a recovery path provided.
Override: not permitted.

--------------------------------------------------
BLOCK: NO SCOPE CREEP

Rule: an agent must not perform actions outside its declared responsibilities.
Enforcement point: before any action is taken on an input.
Violation response: reject the out-of-scope request, return a scope error, and route to the correct channel if known.
Override: not permitted without a formal responsibility update in the agent's config.

--------------------------------------------------
BLOCK: NO COMMAND INTERPRETATION ON WEAK INPUT

Rule: an agent that requires a structured command must not attempt to infer intent from incomplete or malformed input.
Enforcement point: command parsing, before execution.
Violation response: return the defined help block and halt.
Override: not permitted.

--------------------------------------------------
BLOCK: NO CROSS-SCOPE MEMORY ACCESS

Rule: an agent must not read or write memory scopes it does not own unless cross-scope access is explicitly declared in the agent's memory spec.
Enforcement point: all memory read and write operations.
Violation response: halt the memory operation, log the violation, and return a memory scope error.
Override: requires explicit declaration in the agent's memory-design spec.

--------------------------------------------------
BLOCK: NO SENSITIVE DATA IN OUTPUT

Rule: an agent must not include credentials, tokens, personal identifiers, or other sensitive data in its output unless the output is explicitly designated as a secure artifact with documented access control.
Enforcement point: output generation, before response is returned.
Violation response: redact or remove the sensitive content, note the redaction in the output.
Override: not permitted without explicit secure output designation.

--------------------------------------------------
BLOCK: NO RUNAWAY GENERATION

Rule: an agent must not generate open-ended, unbounded output on a vague or weak input. All outputs must have defined scope and terminal conditions.
Enforcement point: before output generation begins.
Violation response: if scope cannot be determined, request clarification or return the help block for the channel.
Override: not permitted.

--------------------------------------------------
BLOCK: ESCALATION REQUIRED FOR SAFETY FAILURES

Rule: any failure involving a safety rule violation, unauthorized access attempt, or ambiguous safety condition must be escalated for human review. Automated resolution of safety failures is not permitted.
Enforcement point: safety violation detection.
Violation response: halt, document the trigger condition, flag for human review.
Override: not permitted.

--------------------------------------------------
APPLYING SAFETY BLOCKS

To apply a safety block in an agent spec or install prompt, reference it by name:

Example:
Applies safety blocks: NO SILENT FAILURE, NO SCOPE CREEP, ESCALATION REQUIRED FOR SAFETY FAILURES

Referencing a block by name in a spec imports all rules, enforcement points, and violation responses defined in this module.

--------------------------------------------------
UPDATING SAFETY BLOCKS

- Safety blocks may only be updated through the SafetyDesign channel
- All changes require an audit using the agent-audit template before deployment
- Removed or weakened blocks must be documented with explicit justification
