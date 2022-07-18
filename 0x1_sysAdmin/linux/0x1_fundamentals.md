# LINUX COMMANDLINE/TERMINAL BASICS

Navigating the filesystem
Files & Directory commands & operations
Input/Output redirections
Searching for file(s) & directories
System information
Text manipulations
Finding informations on commands

## Navigating the filesystem
* List files & Directories
	`ls` - displays list of files/directories the current working directory (folder). Hidden files/directories are not shown by default. Given `ls` some options/arguments changes its' behavior. Short options are usually preceeded by a -. Example: `ls -a`, `ls -l`.
	`dir` -   Similar to ls

	`ls` - Lists contents of a directory excluding hidden files
	`ls -a` - Lists all content of a directory including hidden files/directories
	`ls -l` - Lists contents of a directory excluding hidden files/directory

	You can specify a directory you want its' contents to be listed.
	`ls /etc` - Lists the contents of /etc directory
	`ls -lh /home` - Lists the contents of /home in a listing format with human readable size information.
* Change Directory
	`cd` - Use this command to change/move from the working directory. Typing just `cd` and pressing enter changes you to $HOME directory. The `cd` command takes some few arguments. More info at `help cd` on the command line.

	`cd` - Changes current working directory to $HOME
	`cd /etc` - Changes working directory to `/etc`.

	`pwd` - shows your current working directory.

### Summary
The shell provides mechanism to navigate the command line. `cd` to change directory, `ls` to list contents of a directory and `pwd` to know the current working directory.
Read more from the manuals and help infos.
	```
	man ls		# man pages for ls
	help cd 	# Help for cd shell builtin.
	help pwd 	# help for pwd shell builtin.
	```

## Files & Directories
* Create file(s)
* Create Directory
* Copy | Move Files or Directory
* Create a link to File or Directory
* Delete File(s) or Directories

##
## System Locale & Date and Time
Display/Configure date and time, System wide Locale settings

* date 
	```bash
	$ date # prints current date and time to terminal
	```

* datetimectl command (prints date and time in more details)
 	```bash
	$ datetimectl
	```
	More information can found in ```man date, man timedatectl```

* System wide locale settings.
	config file **/etc/locale.conf** is read during early boot stage by systemd daemon.
	All services on the system inherits this config. Service or user config can override the system wide locale config.

	List available system locales
	```bash
	$ localectl list-locales # List locales
	```

	Check status of current system local
	```bash
	$ locatectl status # prints the current system locale
	```

	set or change system locale
	```bash
	$ localectl set-locale LANG=en-Br
	```
	Read more from the man page ```man localectl```

[Top](./0x0_guide_linux_admin.md)

