Agent specification template for the ResourceGenerationSystem.

Use this template to define a complete, deployable agent. Every section is required unless marked optional.

--------------------------------------------------
AGENT NAME

[Exact name of the agent. Use lowercase hyphenated format for system identifiers.]

--------------------------------------------------
PURPOSE

[One to two sentences describing what this agent exists to accomplish. Be specific. Do not use vague language.]

--------------------------------------------------
RESPONSIBILITIES

[List every responsibility this agent owns. Each item must describe a concrete action or decision this agent performs.]

-
-
-

--------------------------------------------------
NON-RESPONSIBILITIES

[List what this agent explicitly does not own or handle. Prevents scope creep and routing confusion.]

-
-
-

--------------------------------------------------
SCOPE

[Describe the boundaries of this agent's operation. What inputs does it accept? What systems does it interact with? What is always out of scope?]

--------------------------------------------------
BOUNDARIES

[Define hard operational limits: maximum input size, response length, supported modes, disallowed operations.]

-
-
-

--------------------------------------------------
CAPABILITIES

[List all capabilities this agent provides. Each capability should map to a named function or behavior.]

-
-
-

--------------------------------------------------
INPUTS

[Define the input schema. For each input field, specify: name, type, required/optional, constraints.]

Field: 
Type: 
Required: 
Constraints: 

--------------------------------------------------
OUTPUTS

[Define the output schema. For each output field, specify: name, type, always present/conditional, format.]

Field: 
Type: 
Present: 
Format: 

--------------------------------------------------
RULES

[List all behavioral rules in the form: if [condition] then [defined response]. Each rule must be atomic and testable.]

-
-
-

--------------------------------------------------
TOOL USE

[List any tools this agent depends on. For each tool: name, purpose, required/optional, version if relevant.]

Tool: 
Purpose: 
Required: 

--------------------------------------------------
MEMORY AND CONTEXT ASSUMPTIONS

[State what memory or context this agent requires at invocation. If none, state explicitly: no memory dependency. If context is required, specify source and format.]

--------------------------------------------------
FAILURE HANDLING

[For each identified failure mode, define the named response. No silent failures.]

Failure mode: 
Response: 

--------------------------------------------------
EXTENSION POINTS

[Optional. List integration points where this agent can be extended, composed with other agents, or accept additional modules.]

-
-
