```Declutter your mind; follow the sound way.``` [Unix Warlord Wu]

## A LINUX SYSTEM

A running Linux system is made up of many parts put together to serve specific job in the system.
* The Hardware
* The Linux kernel
* The GNU utilities
* Graphical Desktop Environment (WMs|GUIs)
* Application software

* Hardware

* Kernel (Core of a Linux System)
At the core of every linux system is the kernel. First created by Linus Torvalds as copy of Unix system.
The kernel controls all the hardware and software	on the system.
And allocating hardware when necessary, executing software when required.

The four primary functions of the kernel are:
- System memory management
	Manages physical memory; creates and manage virtual memory
	Swap space on is created on the hard drive; the kernel swaps the content of the virtual memory back and forth from the swap space to the physical memory

	Memory locations are grouped into blocks called pages. Each page is located in physical memory or swap space.
	The kernel maintains a table of memory pages that indicates which pages are in physical memory and which pages are swapped out to disk. Swapping out is the process of copying unused memory pages out to swap area

- Software program management
	A running program in a linux system is called a process. A process can be foreground or background.
	The kernel controls how the system manages all the process running on the system.

	The init process is created by the kernel. It starts all other processes. The kernel loads the init process in the virtual memory when it starts.
	Linux OS uses init system that utilizes run levels. A run level directs the init process to run certain process as defined in /etc/inittabs file or the /etc/rcX.d directories.
	There are five init run levels:
		- Run level 1 (Single-user mode): Basic system processes, started along with one console terminal.
			Often used for emergency maintainance. Only the root user can login in this mode.
		- Run level 3 (Multi-user mode): The standard init run level. Various supported services are started.
			Support several console terminals.
		- Run level 5 (Graphical mode): Multi-user mode with x/graphical window system

- Hardware management
	Devices attached to a linux system needs driver code in other to function. The code must be inserted in the kernel. Driver code act as a middle man between application and the hardware.
	The two ways for inserting driver code into the kernel are:
	- Drivers compiled in the kernel
	- Driver modules added to the kernel: Allows driver modules to be inserted/removed in a running linux kernel without having to recompiling the kernel.

	Special files (Device file)
	Linux identifies hardware as special files. Classification device files
	- Character: Used for devices that handle data ONLY one character at a time.
		Most moderms and terminals are in this category.
	- Block: Devices that handle data in large blocks at a time. Eg: Hard drives
	- Network: Used for devices that use packet to send/receive data. Devices such network cards and special
		loopback devices that communicate using networking programming protocols.

	Nodes
	A node is created for each device on a linux system. All communications with the device is performed through the device node.
	Each node has a unique number pair that identifies it to the kernel.
	The number pair includes major and minor device number. Major number for similar device group. Minor number is for identifying specific device within major device group.

- Filesystem management
The linux kernel support many different filesystems to read/write data to/from hard drives. The kernel must be compiled to support the types of filesystems it will use. Some standard filesystems include ext(2|3|4), hpfs, jfs, nfs, proc, ntfs, smb, raiserfs, msdos vfat, XFS ,ISO 9660, ufs and many others. 
Any hard drive must be formatted with a known filesystem before a linux system can access it.
See the linux man pages for supported filesystems (man filesystems).

Virtual File System (VFS)
The standard kernel interface for communicating with any type of filesystem. It caches information as each filesystem is mounted and used.

* The GNU Utilities
Whiles the kernel control hardware devices, operating systems need utilities to perform standard functions such as files and program.
The GNU project was mainly designed for Unix system administrators to have Unix-like environment available.

GNU develop a complete set of Unix utilities under Open Source Software (OSS) philosophy. OSS philosophy allows programmers to develop programs and released it for free without any license.
Linux kernel and GNU OS utilities created a complete, functional free OS - GNU/Linux Operating System.

The Core GNU Utilities
The core bundle of utilities is called _coreutils_. It consists of three parts. Each group consists several utility programs.
- Utilities for handling files
- Utilities for manipulating text
- Utilities for manageing processes

The GNU/Linux shell is a special interactive utility. Provides a way for users to start/stop programs, manage files and manage running processes. The command prompts part of the shell allows user to enter commands, interpretes and executes them in the kernel.

The shell contains a set of internal commands used to control things such as:
	- Copy|Move|Rename files
	- Display currently running programs
	- Stopping running programs
Group of shell commands can be put into files to execute as a program known as shell scripts.

Different shells with different characteristics are available on GNU/Linux system. The default shell on a linux system is the bash shell. Some linux shells include ash, korn, tcsh and zsh. (/etc/shells)

* The Linux Desktop Environment
GNU/Linux OS in it early days had a simple text interface which allow administrators to control the OS.
Several graphical desktop exist for linux systems.

The X Window System Software
The core element in presenting graphics. Works directly with the video card and the monitor.
It controls how a linux system present fancy windows and graphics on the computer. X Window package for linux system include X.org, Wayland and Ubuntu Mir for use with Desktop environments.

An installation GNU/Linux OS attempts to detect installed video card and monitor, then creates an X Window configuration of required information.
The core X Window software produces a graphical display environment that can be used to run individual applications. Does not provide means to manipulate/manage files or launch programs.

Desktop Environment (DE)
A DE on top of X window system software provide means to launch programs, manipulate files and other functionality. Examples of GDE includes: KDE, GNOME, Ubuntu Unity and others.
Uses a fair amount of system resources to run.

Other lightweight DE and window managers that provide basic graphical features with low-intensity on memory and system resources. Examples include Xfce, Mate, Fluxbox, qTile, dwm and others.

Graphical Interface Elements
- Client: Requests graphical services. Eg: Browser, terminal emulator etc.
- Display server: manages the display and input devices (Screen, mouse, keyboard, touch screen)
	Eg: Wayland Compositor, Xserver, Mir
- Window manager: add borders to windows and provide features to move and manage windows. 
	Eg: Compiz, Kwin etc
- Widget Library: add menus and appearance items for desktop environment clients. Eg: Athena, X Intrinsics

### Linux Distributions
Linux distribution (distro) is a complete linux system package i.e. comprises the linux kernel, GNU utilities and a shell and other packages.
Most distros are customized for specific user group. Each customized distro contains the software packages required to support specialized functions. Division of linux distros:
- Full core Linux distributions:
	Provides a complete linux installation including one or more GDEs and linux applications compiled for the kernel. Some core distros include Slackware, Red Hat, Gentoo, Debian, OpenSUSE.
- Specialized distributions:
	Based on the core distros but contains a subset of applications for specific use. Additional customized software. Help in autodetecting and autoconfiguring common hardware devices to simplify installation.
	Examples include Ubuntu, CentOS, Puppy Linux, Kali Linux and many others.
- LiveCD test distributions:
	Boot and run complete linux distribution without installation on the hard drive. Provides an easy and excellent way to test many distributions. Some include Knoppix, Slax, Ubuntu and many other distros provide a liveCD.

## THE LINUX SHELL
Linux system administrators usually interact with the system through Command Line Interface (CLI) provided by the shell. The CLI allows text input and display only text output and some basic graphics output.

* Console Terminals places the Linux system in text mode.
	Several virtual consoles are created when a Linux system starts up. Virtual consoles runs in memory.
	Using ctrl+Alt and f1-f7 keys to access virtual consoles.
	setterm command with options can be used to manage the appearance of virtual console.
* Graphical terminal Emulators Simulates working on a console within graphical desktop window.
- Gnome Terminal Emulator
- Konsole Terminal Emulator
- xterm Terminal Emulator

## BASH SHELL COMMANDS







# LINUX INTERNALS
Describes functions of kernel, underlying structures and implementations.
The kernel uses advance C techniques & GNU C compiler features.

Layers of Abstraction in a Linux System.

Hardware -> Kernel -> User Process

## User Mode
* Has restricted access to a subset of memory and a safe CPU

## Task of the kernel
* An intermediary between the hardware & software in technical terms
* Manages running processes
* Passes application requests to the hardware
* Low-level driver to address device and components of the system
* Kernel can be regarded as an enhanced machine which abstracts the computer on a higher level
* Acts as a resource manager; shares availables resources between various system process
* Ensures system integrity
* Acts as a library which provides system-oriented commands known as system calls for sending request
  C standard library for the Linux Kernel.
* Code running in kernel mode has unrestricted access to system resources (Kernel space).
* Splits memory into subdivisions and maintains states information of subdivisions.
* Acts as interface between hardware and process.

## Hardware
* The main memory:
	Storage with 0s and 1s (bit) and all input and output pass through the main memory
	Kernel and processes resides in it.
* The CPU
	Operates on memory; reads instruction(s) from and writes back to it.

## Kernel

### Kernel Implementations Strategies
* MicroKernels
Only elementry functions are implemented directly in the central kernel
All other functions are delegated to autonomous process that communicate with central kernel via interfaces
ensures dynamic extensibility and ability to swap components at runtime

* Monolithic Kernels
Entire kernel code and subsystems and drivers are packed into a single file.
Each function has access to all other parts of the kernel and has greater performance than microkernel.

Linux OS uses this approach but introduced the concept of modules which allows insertion and removing of functionality at runtime.

** Elements of the Linux System

	* USERSPACE {
				APPLICATION
				C LIBRARY
		}
					|
					|
 		SYSTEM CALL (APIs)
					|
					|
	* KERNEL SPACE {
				KERNEL CORE
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



### PROCESS MANAGEMENT: PROCESSES, TASK SWITCHING, AND SCHEDULING
Starting, Pausing, Resuming and Terminating Processes.

Programs running on unix-like systems are referred to as processes.
Each process is assigned address space in the virtual memory and are independent of other processes
Special kernel mechanism is used to communicate between different processes

Linux is a multitasking system that supports concurrent execution of several process
The kernel switch between processes at short interval that gives the impression of simultaneous processing



## MISCELLANIA
### Hardware


* Process Management:
	Interrupt; Context Switch; Time Slice; Multitasking;
	The kernel runs between process time slices during context switch.

* Memory Management: 
	- Kernel memory area inaccessible to user space process
	- Each user process needs its own section of memory
	- A user process may not access another user process memory section
	- Some memory in user processes can be read-only
	- The system can use more memory than is physically present
	Modern CPUs include MMU; enables virtual memory access
	MMU translates & maps virtual memory to physical memory
	Initialize and maintains the map between virtual and physical memory.
	Memory Address map is the page table.

* Device Drivers and Management
	- Device is typically accessible in kernel mode
	- Improper access could crash the system
	- Device drivers presents uniform interface for device access

### System Calls (syscalls)
The act of opening, reading and writing involves system calls
_fork_ and _exec_ syscalls creates an identical copy of a process and the kernel starts the process to replace it.
	
### User space
Process is simply a state or image in memory.

### Users
An entity that runs processes and owns files; associated with username. 
Kernel identifies users with numeric _userids_.
Userspace processes haver user owner; user may terminate, modify the behavior of its own process.
A user may own files and may choose to share them with others or not.

Linux is a multi-user system. The most important user is the _root_ or _superuser_ (Administrator).
The root user may be able to terminate/modify other peoples processes and read any files on the local system.






























