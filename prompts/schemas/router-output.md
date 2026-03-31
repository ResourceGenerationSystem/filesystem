Router output schema for the ResourceGenerationSystem MasterRouter channel.

This file defines the strict output format that the MasterRouter must produce for every routed request.

--------------------------------------------------
SCHEMA VERSION

Version: 1.0
Applies to: MasterRouter channel output

--------------------------------------------------
REQUIRED FIELDS

Every MasterRouter output must include all of the following fields in the order specified:

1. Primary channel
Format: plain text, single channel name
Constraint: must be exactly one of the valid channel names listed below
Example: PromptDesign

2. Secondary channels (optional)
Format: comma-separated list of channel names, or "none"
Constraint: each entry must be a valid channel name; list must not include the primary channel
Example: SkillBuilder, ToolBuilder

3. Trigger activated
Format: trigger category name in uppercase
Constraint: must match a defined trigger category from the trigger system
Example: SOURCE TRIGGER

4. Enhanced prompt
Format: full enhanced prompt text, ready for execution
Constraint: must be a complete, unambiguous, implementation-ready prompt
Constraint: must apply all applicable enhancement pipeline rules

5. Routing rationale
Format: one to three sentences explaining why the primary channel was selected
Constraint: must reference specific content from the input prompt that determined the routing decision

--------------------------------------------------
VALID CHANNEL NAMES

AgentBuilder
PromptDesign
ReasoningDesign
SkillBuilder
ToolBuilder
WorkflowDesign
MemoryDesign
ContextBuilder
TestingDesign
SafetyDesign

--------------------------------------------------
OUTPUT TEMPLATE

Primary channel: [channel name]
Secondary channels: [channel names or none]
Trigger activated: [trigger category]
Enhanced prompt:
[full enhanced prompt text]

Routing rationale:
[one to three sentence explanation]

--------------------------------------------------
VALIDATION RULES

- Primary channel must be a single valid channel name; no variations, prefixes, or suffixes
- Enhanced prompt must not contain unresolved placeholders
- Enhanced prompt must be self-contained unless external dependencies are explicitly declared within it
- Routing rationale must not be empty
- Output must not include fields beyond those defined in this schema without explicit version update
