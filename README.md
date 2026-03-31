# ResourceGenerationSystem Filesystem

This repository stores the backend prompt, enhancer, trigger, and schema modules for the ResourceGenerationSystem project. It serves as a modular, source-aware prompt operating system backend, not a storage repository for generated outputs.

## Purpose

This repository provides the configuration and context base that powers the ResourceGenerationSystem routing, agent behavior, and prompt compilation pipeline. All modules are plain-text, production-oriented, and designed to be reusable across channels.

## Folder Structure

### prompts/entry/

Starter prompts for each channel in the ResourceGenerationSystem. Each file defines the role, responsibilities, and behavior rules for a specific channel.

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

### prompts/triggers/

Trigger definitions used by the routing layer. `keywords.md` contains the full list of recognized trigger keywords, their categories, and expected behaviors.

### prompts/schemas/

Strict output format definitions. `router-output.md` defines the required output structure for the MasterRouter channel.

## Additional Structure

### agents/

Per-agent configuration files defining connection and capability settings for each channel agent.

### config/

Global configuration files including the master router config and network registry.

### models/

Model connection and data-access configuration files.

### runtime/

Runtime state files including task queues and pending job tracking.

## Design Principles

- Modular: each file is independently usable
- Source-aware: designed for GitHub-backed prompt module retrieval
- Future-ready: compatible with GitHub connectors, external APIs, MCP tool systems, and dynamic module loading
- No generated outputs are stored here