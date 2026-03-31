Enhancement module for the MemoryDesign channel.

This module supplements the global enhancer with MemoryDesign-specific prompt improvements.

--------------------------------------------------
MEMORYDESIGN ENHANCEMENT RULES

When enhancing a prompt routed to MemoryDesign, apply:

1. Require memory type classification
- Ensure the memory module is classified as short-term, long-term, episodic, semantic, or procedural
- Add classification requirement if missing

2. Require scope definition
- Ensure the memory module defines which agent or session scope it belongs to
- Add scope boundary requirements if absent

3. Require write and read condition definitions
- Ensure the prompt specifies when memory is written and when it is retrieved
- Add explicit condition definitions if missing

4. Require retention and expiration policy
- Ensure the prompt defines how long data is retained and what triggers cleanup
- Add a retention policy requirement if absent

5. Require isolation rules
- Ensure the prompt specifies what cannot be shared across memory scopes
- Add isolation requirements if the spec allows uncontrolled cross-scope access

--------------------------------------------------
OUTPUT STRUCTURE ENFORCEMENT

Every MemoryDesign output must follow this section order:
1. Memory Type and Classification
2. Scope and Ownership
3. Storage Format and Key Structure
4. Write Conditions
5. Read Conditions and Retrieval Logic
6. Retention and Expiration Policy
7. Isolation Rules
8. Failure Handling

--------------------------------------------------
QUALITY ADDITIONS

- Require that retrieval logic is deterministic for equivalent queries
- Require explicit documentation of any cross-scope data sharing
