Global enhancement module for the ResourceGenerationSystem prompt pipeline.

This module applies to all channels unless overridden by a channel-specific enhancer.

--------------------------------------------------
UNIVERSAL ENHANCEMENT RULES

Apply these rules to every prompt before routing or execution:

1. Clarify intent
- Restate the objective in one precise sentence
- Remove ambiguous phrasing

2. Define output type
- Specify what the response must be: specification, plan, list, schema, analysis, or other
- Specify format: markdown, plain text, structured sections, or other

3. Add structural requirements
- Require section headers for responses longer than three paragraphs
- Require numbered steps for sequential processes
- Require bullet lists for rule sets and constraints

4. Add quality requirements
- Output must be implementation-ready without further clarification
- Output must be self-contained unless external dependencies are explicitly declared
- Output must use precise, unambiguous language

5. Add safety requirements
- Output must not contradict defined safety rules
- Output must not include instructions that violate system constraints

6. Remove vagueness
- Replace phrases such as "as appropriate", "if needed", "handle accordingly" with explicit conditions and defined responses

--------------------------------------------------
ANTI-PATTERNS TO REMOVE

- Vague action verbs without defined outcomes
- Undefined scope boundaries
- Open-ended loops without exit conditions
- Unstated assumptions about agent capabilities or context availability

--------------------------------------------------
APPLICABILITY

This module is always active. Channel-specific enhancers supplement it, they do not replace it.
