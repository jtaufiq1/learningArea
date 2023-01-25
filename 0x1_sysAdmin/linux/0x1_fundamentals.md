# LINUX COMMANDLINE/TERMINAL BASICS
- [x] The Command Shell
- [x] Standard Streams & Input/Output Redirections
- [x] Shell Globbing
- [x] Shell & Environmental variables
- [x] Navigating the filesystem
- [x] Files & Directory commands
- [x] Creating Files/Directory links
- [x] Files & Directory Permissions
- [x] Find & Search File(s) | Director(y|ies)
- [x] Text tools & Text Editors
- [x] Finding more informations
- [ ] System information & Configuration

## The Command Shell
The shell is a program that runs commands. Serves as a programming environment.
Shell scripts are sequence of commands in a text file.

Linux uses an advance version of the unix shell known as Bourne-Again Shell (bash). The default on most ditros.

A shell window in a GUI environment is called a Terminal. 
A shell has a prompt and usually ends with $ for the normal user and # for the root user.
```sh
	# E.g. of a shell prompt: user@hostname:path$
	tgh@kali:~$ echo "Welcome to Linux Shell #USER"
	tgh@kali:/$ echo "I am in the top-level of the directory (root-dir)"
	thg@kali:/etc/$ cat passwd # Display the content of passwd to stdout
```

## Standard Input and Output Streams
Unix/Linux processes uses I/O streams to read & write data
Streams allows easy manipulation of input & output sources other than the default
Process reads data from input stream and writes data to output stream.

Sources of input stream can be a file, device, terminal or output from another process
Errors during input/output redirections prints to the default output stream
Standared Error (stderr) output can be redirected.

ID Stream
0 - stdin (Standard Input)
1 - stdout (Standard Output)
2 - stderr (Standard Error)
```sh
	# command > output 	- Output redirection
	# command >> output - Append (Output redirection)
	# command < input	- Input redirection
	# command | command - Pipe: output of command becomes input of another command

	## STDIN (<) - Default is keyboard
	$ cat < path/to/file 
	$ head < file_name
	
	## STDOUT (>, >>)
	$ echo "Some text to stdout"		# Print argument(s) [text] to stdout
	$ cat [file1] [file2]				# Print content of file(s) or stdin to stdout
	# 
	$ echo "Redirection" > out			# Output of echo is sent to out not the terminal
	$ cat file1 file >> out 			# Append the output of cat to 'out' not the terminal
	
	## STDERR (2>)
	$ ls not_existing 2>error_file 		# Error of ls command is sent to 'error_file'
	$ ls -A not_existing > output 2>&1 	# Output and error message are sent to 'output'
	
	# Pipe (|)
	$ cat /proc/cpuinfo | tr a-z A-Z 	# The output of cat becomes input to tr
	#									  Transforms output of cat
	$ head file | rev 					# Reverses the output of the head command
	#
	## Error Messages
```

## Shell Globbing
Use to match simple file and directory names. The shell matches globs to filenames.
Expansion: The shell substitutes the filenames for the _globs character_ and then run the revised command line.
Single quote around glob in a command prevents expansion.
```sh
	$ echo * 						# Matches and expand any number of arbitrary characters
									# echo: if no filename matches the glob, the shell performs no expansion
	$ echo '*' 						# No Expansion: Literally sent to output. Same for '?'
	$ ls * 							# Matches and expand all filenames
	$ ls ? 							# Matches filename/directory with single character
	$ echo ?r* 						# Matches any filename starting with a single char followed by r and any chars
```

## Shell & Environmental Variables
For keeping tracks of values in scripts
Variables controls the way the shell behaves and keeping track of values in script.

Shell variables are limited to the instance of the shell in which it is defined
Environmental variables are accessible by all processes running in a shell.
```sh
	$ VARIABLE_NAME=value		# Create and Assign value to variable
	$ export VARIABLE_NAME 		# Create an environmental variable

	$ echo $VARIABLE_NAME		# Display value of a variable
	$ printenv [VARIABLE_NAME]	# List all current environmental variables
	$ env [command]				# Run a command in a modified environment|prints all environmental if no arg

	$ unset VARIABLE_NAME		# Remove/unset shell/environmental variable

	## Common Environmental variables
	# USER 	- contains the current user username
	# HOME 	- contains current user's home directory
	# PATH 	- Contains list of directories to look for executables/commands
	# PWD  		- Present Working Directory
	# LOGNAME 	- Log name
	# EDITOR 	- Specifiers default text editor
	# LANG 		- User's Language
	# MAIL 		- User mail
```

## Navigating the filesystem

* File system is a laid as a directory tree; with a single root (/).
All other directories have parent directory and every file is also contained in a directory.

```sh
	# tree [ARGS] [PATH]
	$ tree 				# Show the directory tree
```

* Special Subdirectories (.|..)
- (.) Specifies the current working directory.
- (..) Specifies the parent directory.

* Absolute and Relative Paths
  Path can be Absolute or Relative path. Relative path is relative to the current directory.
  - Absolute path have the full path specified. Starting from the root (/) tree. Eg: /home/taufiq/documents.
  - Relative/Reflexive path are relative to the current working directory or parent of working directory. Eg: doc/dirs  

* Show the current working directory
```sh
	$ pwd 			# Shows your current working directory
	$ pwd -P
	$ echo $PWD 	# Print Working Directory (PWD) environmental variable points to the current working directory.
```

* Change Directory
Use to change working directory.

```sh
	$ cd 		# Changes current working directory to $HOME
	$ cd .. 	# Changes to the parent directory (cd . # Current Working Directory)
	$ cd /etc 	# Changes working directory to /etc.
	$ help cd 	# More info on usage 
```

* List Content(s) Directories
displays list of files/directories the current working directory (folder). Hidden files/directories are not shown by
default. Given some options/arguments changes its behavior. Short options are usually preceeded by a dash (-).

```sh
	$ ls [file|directory]	# List file|directory content. Defaults to current directory.
	$ ls -A					# List all including hidden files (Files that start with period(.))
	$ ls -a					# List all including hidden file and relative path to current & parent directory
	$ ls -l 				# Long list format with more informations
	$ ls -d 				# List directory information instead content
	$ ls -Al 				# Mixed options
	# More ls options: -F classify; -C column view;
	$ dir 		# Shell builtin similar to ls

	# You can specify a directory you want its contents to be listed.
	$ ls /etc 	# Lists the contents of /etc directory
	$ ls -lh /home # Lists the contents of /home in a listing format with human readable size information.
	$ # Filtering Output
	$ ls ?					# List files/Directories with single name(s)
```

## Files & Directories

* Create file(s) & Directories
```sh
	$ touch filename 			# Creates an empty file
	$ mkdir directoryName 		# Creates a directory/folder
	$ mkdir -p parent/child		# Creates parent directory if not existing and child directory
```

* Copy & Move File/Directories
```sh
# Copy | Move/Rename Files or Directory
	$ cp src dest 				# Copy's source to destination
	$ cp -R src_dir dest_dir	# Duplicate source directory to destination directory 

	$ mv src dest 				# Move from source to destination or Rename source to destination
```

* Determining a file type
```sh
	$ file [file]				# Find the type of file
```

* Create a link to File or Directory
```sh
	$ ln source target 		# Create a link of source as target
	$ ln -s source target 	# Create a symbolic link of source as target
```

* Delete File(s) or Directories
```sh
	$ rm filename			# Remove file
	$ rm -f directoryName	# Force remove a file or non-empty directory
	$ rm -rf file/directory # Force remove a non-empty directory recursively
	$ rmdir non-empty-directory
```

## File & Directory Permissions
```sh
	# PERMISSIONS: READ|WRITE|EXECUTE
	# USER:		   OWNER|GROUP|OTHERS
	# BIT:		   SETUID|SETGUID
	#
	# View Permission
	$ ls -l [File]
	#
	# Setting/Changing Permission
	$ chmod [-/+][MODE] [FILE|DIR] 			# MODE: r:1, w:3, x:4, All:7; u:owner, g:group, o:others, a:all
	#									      Fields: S,u:rwx,g:rwx,o:rwx 0777
	$ chmod u+rwx [FILE|DIR]				# Set READ|WRITE|EXECUTE for owner of the file
	$ chmod a=rwx [FILE|DIR]				# Set READ|WRITE|EXECUTE for all USERS equivalent to chmod 0777 [FILE|DIR]
	#
	# Changing Owner/Group
	# chown [ARGS] USER:[GROUP] [FILE|DIR]
	$ chown taufiq:wheel [FILE|DIR]			
	$ chown -R user:group [DIR]				# Recursive change the owner/group of Directories and content.
```

## Find & Search Commands and Files

* Locate a command(s) using `which` & `whereis` Command
```sh
	$ which cmd 			# Locate a command/program in user's $PATH
	$ which $SHELL			# Find the location of the default shell ($SHELL Environmental variable)

	$ whereis command		# Locate command/program, source and manuals (documentation)
	$ whereis ls 			# The location of ls and documentations
	$ whereis -b ip			# Find the binary location of ip
	$ whereis -m whoami 	# The manual location of whoami
	$ whereis -s wget		# The source location of wget command

	# Using the -B -M -S path options, the search can be limited to a path
```

* Locate & Mlocate Database
```sh
	$ # Quickly find files with locate in mlocate database(s)
	$ # mlocate package must be installed 
	$ # run updatedb to update mlocate's database(s)

	$ updatedb					# Update locate database
	$ locate file_name 			# Find the location of file in the database
```

* Find Command
```sh
	$ # find [path] [options] target
	$ # Supports more options to refine the search
	$ find [PATH] -name [file] -print		# Find text starting from the current directory
	$ find / -name file_name -type file_type -print
```

## Text Tools & Text Editors

* Basic Text Manipulation Tools
```sh
	$ cat [File 1] [File N]			# Print contents of files to STDOUT
	$ cat -n [File] [File N]		# Number each line and print it out
	$ cat -b [File] [file N] 		# Same as above except add number to non blank line(s)

	$ head -n N [file] 				# Print first N lines of file

	$ tail -n N [File]				# Output N lines of a file 
	$ tail -f|[-F fileName] 		# Output in real time as file grows
	$ tail -f|[-F fileName] -s N 	# Check iteration at every N seconds
	$ tail -f|[-F fileName] --pid P # Terminate after pid P dies
	$ tail -s N --pid P [fileName]	# Checks pid P at every N seconds

	# Pager
	$ more [File]					# Display text page by page
	$ less [file]					# Advanced more: interactive commands; search 

	$ diff [Arguments] File1 File2	# Shows the difference between 2 text files
	
	$ sort 							# Sort lines of text
	$ sort -r						# Sort in reverse order
	$ sort -u [FILE]				# Sort and remove duplicates

	$ uniq [FILE]					# Print lines without duplicates
	$ wc [ARGS] [FILE]				# Count number of characters,Words and lines
	$ wc -c [FILE]
	$ wc -w [FILE]
	$ wc -l [FILE] 

	$ nl 

	# Text Transformation
	$ tr 							# Translate/truncate text
	$ tr [SET1] [SET2] 				# Translate SET1 into SET2
	$ tr -d [SET] 					# Truncate SET

	# Reverse Text/lines
	$ tac
	$ rev
```

* Text Editors
```sh
	# EDITOR=/path/to/editor 		# Default editor environmental variable
	$ vim fileName 					# Edit fileName with vim
	$ nano
	$ emacs
	# ....
```

## Finding Help (More Information)
For more informations on command and usage.

* man page & help for shell builtin
```sh
	$ man cmd							# man pages for ls
	$ help cd 							# Help for cd shell builtin.
	$ help pwd 							# help for pwd shell builtin.
```

* More in /usr/share/docs Directory
* Info Pages: Comprehensive information on a command
* Web search
* Forums & Blogs

## System Information and Configuration

* Current Logged in user(s)
```sh
	$ whoami
	$ who
	$ w
	$ uptime
	$ uname
```

### System Locale & Date and Time Configuration
Display/Configure date and time, System wide Locale settings

* date 
```sh
	$ date 				# prints current date and time to terminal
	$ datetimectl 		# command (prints date and time in more details)

	$ man date 			# Man pages for date contains more information
	$ man timedatectl	# Or timedatectl from systemd
```

* System wide locale settings.
config file /etc/locale.conf is read during early boot stage by systemd daemon.
All services on the system inherits this config. Service or user config can override the system wide locale configuration.

```sh
	$ localectl list-locales 			# List available system locales
	$ locatectl status 					# prints the current system locale

	$ localectl set-locale LANG=en-Br	# Set or change system locale to Brittish English
	$ man localctl 						# Read more from the systemd localctl man pages
```

[Top](./0x0_guide_linux_admin.md)

