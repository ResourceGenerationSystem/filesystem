Trigger keyword definitions for the ResourceGenerationSystem routing pipeline.

This file defines all recognized trigger keywords, their categories, and their expected behaviors when detected in an incoming prompt.

--------------------------------------------------
TRIGGER CATEGORIES

1. DEFAULT
Condition: always active
Behavior: all prompts are enhanced and routed through the standard pipeline

--------------------------------------------------
2. FORCE ROUTE
Condition: a valid channel name is explicitly mentioned in the prompt
Valid channel names:
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

Behavior:
- prioritize the named channel as primary
- override default routing logic unless the named channel is clearly incorrect for the request

--------------------------------------------------
3. IMPROVEMENT MODE
Activation keywords:
refine, improve, optimize, enhance, upgrade, fix, iterate, revise, rework, update, polish

Behavior:
- treat input as an existing artifact to be improved
- preserve the original intent
- upgrade quality, structure, and completeness
- route to the closest matching channel

--------------------------------------------------
4. MULTI-STAGE
Condition: request implies multiple phases, stages, or dependent deliverables
Behavior:
- select one primary channel
- assign additional channels as secondary
- document stage dependencies explicitly

--------------------------------------------------
5. LOW-QUALITY INPUT
Condition: prompt is vague, incomplete, or lacks sufficient detail for routing
Behavior:
- expand aggressively into a usable, complete prompt
- do not ask for clarification unless the request is fundamentally unresolvable
- apply maximum enhancement before routing

--------------------------------------------------
6. SOURCE TRIGGER
Activation keywords:
github, repo, repository, module, enhancer, template, spec, schema, file, config, source, sources, reference

Behavior:
- consult connected sources or web search when available
- if source access is unavailable, simulate standardized source-based enhancement logic
- prioritize reusable structures, templates, schemas, and modules in output

--------------------------------------------------
7. CONTROL TRIGGERS

These are intentional control phrases. They must not be interpreted casually or activated by partial matches.

Trigger: startRGS
Behavior:
- activate full routing and enhancement behavior
- treat the message as a formal ResourceGenerationSystem request
- prefer source-aware enhancement when relevant

Trigger: sourceRGS
Behavior:
- prioritize connected sources, repo-backed modules, templates, and configs
- if unavailable, continue with simulated module logic

Trigger: refineRGS
Behavior:
- force Improvement Mode
- assume the user wants an existing prompt, agent, workflow, or spec upgraded

Trigger: routeRGS
Behavior:
- prioritize fast classification and exact channel assignment
- minimize unnecessary expansion unless needed for quality

Trigger: buildRGS
Behavior:
- assume the user wants a production-ready creation prompt
- include concrete deliverables, constraints, and quality requirements

--------------------------------------------------
TRIGGER PRIORITY ORDER

When multiple triggers are active, apply in this order:
1. CONTROL TRIGGERS (highest priority)
2. FORCE ROUTE
3. SOURCE TRIGGER
4. IMPROVEMENT MODE
5. MULTI-STAGE
6. LOW-QUALITY INPUT
7. DEFAULT (lowest priority, always active)
