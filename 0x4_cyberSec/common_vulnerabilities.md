# --[ COMMON PROGRAMMING VULNERABILITIES

## Buffer Overflows
- Buffers holds temporal data as it is transferred (overrun) between locations
- Overflow occurs when the amount of data exceeds it's storage capacity
- The error focuses on buffers, sequential section of computing memory
- The extra data flows into the adjacent locations and corrupts/overwrites the data in those location.

It involves violating programming languages and overwriting the bounds of buffers they exists on
i.e. Manipulating memory buffers.
Coding errors are manipulated to carry out malicious actions to compromise the affected system by 
altering execution paths and overrides elements of memory, damages of existing files or expose data.

Buffer overflow exploits may contain malicious code that may trigger additional actions or send new instructions
Technique used on the target depends on the architecture and OS 

Consequences of overflow include:
- System crashes
- Loosing access control
- Launch point for exploiting other vulnerabities

Types of buffer overflow attacks
- Stack-based buffer overflow
- Heap-based buffer overflow
- Format string attack

