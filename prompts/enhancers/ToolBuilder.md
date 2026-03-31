Enhancement module for the ToolBuilder channel.

This module supplements the global enhancer with ToolBuilder-specific prompt improvements.

--------------------------------------------------
TOOLBUILDER ENHANCEMENT RULES

When enhancing a prompt routed to ToolBuilder, apply:

1. Require interface definition
- Ensure the tool has a named, versioned interface
- Add an interface contract requirement if missing

2. Require input validation rules
- Ensure all input parameters have types, constraints, and validation logic defined
- Add validation requirements if absent

3. Require error mode documentation
- Ensure all error modes are named and have defined response formats
- Add error handling requirements if missing

4. Require side effect documentation
- Ensure any side effects are explicitly listed
- If no side effects exist, require an explicit declaration of statelessness

5. Require example invocation
- Add a requirement for at least one example invocation with expected output

--------------------------------------------------
OUTPUT STRUCTURE ENFORCEMENT

Every ToolBuilder output must follow this section order:
1. Tool Name and Version
2. Primary Function
3. Input Schema
4. Output Schema
5. Error Modes
6. Side Effects
7. Authentication Requirements
8. Example Invocation

--------------------------------------------------
QUALITY ADDITIONS

- Require that tool interfaces remain stable; breaking changes must be versioned
- Require that all error responses follow a consistent format: code, message, and recovery instruction
