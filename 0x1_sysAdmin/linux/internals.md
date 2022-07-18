```Declutter your mind; follow the sound way.``` [Unix Warlord Wu]

# LINUX INTERNALS

Describes functions of kernel, underlying structures and implementations.
The kernel uses advance C techniques & GNU C compiler features.

## Task of the kernel
* An intermediary between the hardware & software in technical terms
* Passes application requests to the hardware
* Low-level driver to address device and components of the system
* Kernel can be regarded as an enhanced machine which abstracts the computer on a higher level
* Acts as a resource manager; shares availables resources between various system process
* Ensures system integrity
* Acts as a library which provides system-oriented commands known as system calls for sending request
  C standard library for the Linux Kernel.

## Kernel Implementations Strategies
* MicroKernels
Only elementry functions are implemented directly in the central kernel
All other functions are delegated to autonomous process that communicate with central kernel via interfaces
ensures dynamic extensibility and ability to swap components at runtime

* Monolithic Kernels
Entire kernel code and subsystems and drivers are packed into a single file
Each function has access to all other parts of the kernel
Has greater performance than microkernel
Linux is uses this approach but introduced the concept of modules which allows insertion and removing of functionality at runtime.

## Elements of the Kernel

	* USERSPACE { APPLICATION
			 C LIBRARY
		}
				|
				|
 		SYSTEM CALL (APIs)
				|
				|
	* KERNEL SPACE { KERNEL CORE
	 								DEVICE DRIVERS
	 								VIRTUAL FILESYSTEM
	 								FILESYSTEMS
	 								PROCESS MANAGEMENT
	 								MEMORY MANAGEMENT
	 								NETWORKING
	 								ARCH SPECIFIC CODE
		}
			|
			|
	* PHYSICAL HARDWARE

* NETWORKING
* VIRTUAL FILESYSTEM
* FILESYSTEMS
* DEVICE DRIVERS
* PROCESS MANAGEMENT
* MEMORY MANAGEMENT
* ARCHITECTURE SPECIFIC CODE

### PROCESSES, TASK SWITCHING, AND SCHEDULING
Programs running on unix-like systems are referred to as processes.
Each process is assigned address space in the virtual memory and are independent of other processes
Special kernel mechanism is used to communicate between different processes

Linux is a multitasking system that supports concurrent execution of several process
The kernel switch between processes at short interval that gives the impression of simultaneous processing





