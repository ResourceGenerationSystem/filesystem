Agent build schema for the ResourceGenerationSystem AgentBuilder channel.

This file defines the required structure for agent build artifacts produced by the AgentBuilder channel in build mode.

--------------------------------------------------
SCHEMA VERSION

Version: 1.0
Applies to: AgentBuilder channel output (build mode)

--------------------------------------------------
REQUIRED FIELDS

Every agent build artifact must include all of the following fields in the order specified:

1. Artifact type
Format: plain text
Constraint: must be exactly "agent-install-prompt"
Example: agent-install-prompt

2. Channel
Format: plain text, single channel name
Constraint: must be exactly one of the valid channel names
Example: SkillBuilder

3. Agent name
Format: plain text
Constraint: lowercase hyphenated identifier
Example: memory-agent

4. Core role
Format: one to two sentence description
Constraint: must be specific, not abstract

5. Responsibilities
Format: bulleted list
Constraint: each item must describe a concrete action this agent performs

6. Operating rules
Format: numbered list
Constraint: each rule must use conditional form: if [condition] then [action]

7. Output discipline
Format: bulleted list
Constraint: must include self-containment, failure handling, and no silent failures

8. Acknowledgment
Format: exact string
Constraint: must be the word: yes

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

Artifact type: agent-install-prompt
Channel: [channel name]
Agent name: [agent name]

Core role:
[one to two sentence description]

Responsibilities:
- [responsibility]
- [responsibility]

Operating rules:
1. [if condition then action]
2. [if condition then action]

Output discipline:
- [rule]
- [rule]

yes

--------------------------------------------------
VALIDATION RULES

- Channel must be a single valid channel name; no variations or prefixes
- Agent name must be lowercase and hyphenated
- Operating rules must be conditional; imperative-only rules are not acceptable
- Acknowledgment must be the last line and must be exactly: yes
- No unresolved placeholders in final artifact
