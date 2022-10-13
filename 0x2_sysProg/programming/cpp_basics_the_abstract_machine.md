# --[ **C++ Basics - The Abstract Machine**

**The abstract machines:**
Machines that permit the step by step execution of instructions (programs) by omitting the many details of real (hardware) machines.

It is simply an imaginary computer, capable of executing a program in the source language.

A processor design not intended to be implemented as hardware. But a notional executor of particular intermediate language used in a compiler or interpreter.

Serve as an intermediate language for stage compilation and bridges the gap between high level language and the low level of real machine.

An **abstract machine** has instruction set, register set, and memory model.

It may provide instructions which are closer to the language being compiled than any physical computer or it may be used to make the language implementation easier to port to other platforms.

## The C++ Abstract Machine
C++ defines how programs work in terms of an abstract machine deliberately defined to be "closed to the hardware". `[Bob Steagall - Cppcon 2020]`

C++ abstract machine is the portable abstraction of your *OS*, kernel and hardware.
The abstract machine is the intermediary between c++ program and the system that it is run on.

## Rational Behind *(C++)* Abstract Machine
With wide variety of computing platforms, it's simply impractical to create a separate language and set of tools for every computing platform.

Computing platforms: General purpose CPUs (Intel, AMD, SPARC etc), GPUs and Specialized co-processors (Nvidia, AMD, Intel etc), and Embedded processors (TI, Atmel, FPAG etc).

When we write programs, we mostly don't want to be concerned with the details of the underlying physical hardware. We want tools to help us manage that complexity.

We want language capable of representing the abstraction relevant to the problem domain at hand.

And we want programming language that transforms our programs to executable form on one or more computing platforms:
 - To acomplish complex information processing task
 - To write programs in human-readable language to improve productivity.
 - To use tools that robustly and reliably transform our programs into a form that can execute on one or more computing platforms. (Compiler and linker in c++).

To solve problem like this, we humans like to use **abstraction**. And so we define programming languages in terms of abstract machines. Eg: C, C++, Java, python, Perl, Awk etc.

## The Design of C++ Abstract Machine (Language Goals)
C++ should support:
* Performance critical software
* Software and language evolution
* Fast and scalable development
* Code that is simple and easy to read, write and understand.
* Current hardware architecture, OS platforms and environments as they evolve.

Giving the programmer control over every aspect of the program performance, leaving no room for a lower-level language and a predictable code performance, c++ meets (language) design goals by
* Leaving no layers of abstraction/execution between it and the hardware:
	 - Without interpreters/virtual machines
	 - No intermediate language between c++ and the hardware
	 - And allows for high-quality code generation by the compiler backend.
* C++ maps *(fundamental)* types and operations directly onto hardware (memory entities).
 - Pointers, references, arrays maps directly to hardware addressing capabilities as modern hardware supports useful (complex) arithmetic/logical operations on these entities.

C++ defines how programs work in terms of abstract machine deliberately defined to be close to the hardware.
C++ code is written to target the c++ abstract machine. Programs perform operations on the abstract machine. The implementation translate abstract machine operations into physical machine operations. `[Bob Steagall - Cppcon 2020]`

## The Abstract Machine (C++)
1. Source Code - describe operations on the abstract machine
2. Compiler - Emulates program running on the abstract machine
   - checks for syntax errors and semantic errors
   - emulates program running on abstract machine
   - maps/translate operations on the abstract machine into machine code
3. Machine Code - runs on physical machine

		| Source Code |
			//
		| Compiler |		---> | Abstract Machine |
			\\
		| Machine Code |	---> | Physical Machine |


When we write c++ programs, we are writing to the c++ abstract machine. `[Bob Steagall - Cppcon 2020]`


## --[ Characteristics of the Abstract Machine in C++ Standard

* Implementation: 
	Tools to verify a program on the abstract machine and generate executable image. (Compiler, linker)

* Implementation must emulate the **observable behavior** of the abstract machine:
	*Observable behavior* - Execution state information exchanged over time with outside entities.
	Many possible valie execution paths could occur in the abstract machine; implementation must match one of them.

* Parameterized:
	Implementation-defined and documented allowable behaviors of the abstract machine.

* Non-deterministic:
	Unspecified (undocumented) set of allowable behaviors of the abstract machine

* Operations can be undefined
	No requirements on the behavior of undefined operations.

* Expressions with non-observable side effects may be ignored:
	*Expression* - a sequence of operators and operands that specify a computation.
	*Side effects* - changes in the program execution state.

		[ Source Code ]
			//
			\\
		[ Compiler ]------------------> [ Abstract Machine ]
			\\									|
			//					  `equivalent observable behavior`
			//									|
		[ Machine Code ]--------------> [ Physical Machine ]

**Our programs describe operations performed on the abstract machine. Implementation translates abstract machine operations into physical machine operations.**















