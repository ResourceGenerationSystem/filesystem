# ResourceGenerationSystem Filesystem

This repository stores the backend prompt, enhancer, trigger, schema, template, and module files for the ResourceGenerationSystem project. It serves as a modular, source-aware prompt operating system backend, not a storage repository for generated outputs.

## Purpose

This repository provides the configuration and context base that powers the ResourceGenerationSystem routing, agent behavior, and prompt compilation pipeline. All modules are plain-text, production-oriented, and designed to be reusable across channels.

## Folder Structure

### prompts/entry/

Starter prompts for each channel in the ResourceGenerationSystem. Each file initializes the channel identity and stable operating role.

Channels:
- MasterRouter
- AgentBuilder
- PromptDesign
- ReasoningDesign
- SkillBuilder
- ToolBuilder
- WorkflowDesign
- MemoryDesign
- ContextBuilder
- TestingDesign
- SafetyDesign

### prompts/enhancers/

Category-specific enhancement modules that augment prompts before execution. `global.md` applies to all channels. Each other file applies enhancements specific to its named channel.

### prompts/templates/

Reusable structural templates for producing agent artifacts.

- `agent-spec.md` - complete agent specification template
- `agent-install.md` - deployable agent install prompt template
- `agent-audit.md` - structured agent audit and review template

### prompts/schemas/

Strict output format definitions.

- `router-output.md` - required output structure for the MasterRouter channel
- `agent-build.md` - required structure for AgentBuilder build mode artifacts
- `agent-output.md` - universal agent output structure for all channels

### prompts/modules/

Reusable logic modules sourced by agents and prompts.

- `capabilities.md` - canonical capability declarations and usage rules
- `failure-handling.md` - failure categories, response formats, and hard rules
- `safety-blocks.md` - non-overridable safety constraints for all agents

### prompts/triggers/

Trigger definitions used by the routing layer. `keywords.md` contains the full list of recognized trigger keywords, their categories, and expected behaviors.

## Additional Structure

### agents/

Per-agent configuration files defining connection and capability settings for each channel agent.

Canonical agent folders:
- master-router
- agent-builder
- prompt-design
- reasoning-design
- skill-builder
- tool-builder
- workflow-design
- memory-design
- context-builder
- testing-design
- safety-design

### config/

Global configuration files including the master router config and network registry.

- `masterrouter.cfg` - route table mapping canonical channel names to agent paths
- `network-registry.json` - full agent registry with paths and statuses

### models/

Model connection and data-access configuration files.

- `kimi-k2-5/` - connection and data-access config for the Kimi K2.5 model

### runtime/

Runtime state files including task queues and pending job tracking.

## Design Principles

- Modular: each file is independently usable
- Source-aware: designed for GitHub-backed prompt module retrieval
- Deployable: all artifacts are production-ready without additional transformation
- No generated outputs are stored here
- No placeholders, stubs, or TODO markers in deployed files
