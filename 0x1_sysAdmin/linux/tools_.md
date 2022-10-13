# Tools

## Bourne Again Shell (BASH)

* The Bourne Shell: /bin/sh
```sh
# Default shell on Unix/Linux systems
# Shell runs commands and serve as a programming environment (Script) use to manage task
# Shell scripts: text files with sequence of shell commands
# use chsh command to change the default shell
#
$ echo $SHELL			# Get the current shell
$ which $SHELL			#
$ chsh /path/to/shell	# Change the shell
```

* Wildcards (Globbing & RegEx)
```sh
# Globbing: Allows matching patterns to file or directory names, substitutes all file names
# Runs the revised command line. Substitution is called expansion
# No expansion is made if no file matches the glob & runs with the literal character

# * 	- Matches any number of characters
# ? 	- Matches exactly one character
# [] 	- Specifies a ranges
# {}	- Groupings. Terms are separated with commas
$ man 7 glob # More on wildcards

$ echo * 	# Prints all the files in the current directory
$ ls ?		# Prints all files/directories with a single name

# To prevent expansion, put single quotes ('') around the wildcard; ie: '*', '?'
# Or escape it with backslash (\)
```

* Shortcuts
cntrl + F 	- Move the cursor position one character forward
cntrl + B 	- Move the cursor position one character backward ()

cntrl + A 	- Move the cursor position to the beginning
cntrl + E 	- Move the cursor position to the end

cntrl + P 	- View the previous command (Move the cursor UP)
cntrl + N 	- View the next command (Move the cursor DOWN)

cntrl + W 	- Erase previous word behind the cursor
cntrl + K 	- Erase character(s) at cursor forward to the end
cntrl + U	- Erase character(s) at cursor backward to the beginning of line

cntrl + Y 	- Paste erased text (from ^C + U, ^C + W, ^C + K)
cntrl + L 	- Clear terminal window
cntrl + R 	- Reverse history search

cntrl + xe  - Invoke $EDITOR to edit command at shell prompt

* Shell Builtins
```sh

```

## READING DOCUMENTATION

* info
```sh
$ info 						# Program for reading information ()
# <space_key | del_key> 	Next/Previous window
# <n_key | p_key>			Next/Previous Node of the same level
# <b_key>					Move to the beginning of current node
# <?_key>					Show a quick summary of info commands
# <g_key node string>		Goto specified node string
# <]_key|[_key>				Move to next/previous node

# Menu Navigation
# <m_key subtopic> 			Go to a subtopic in menu
# <control-g>				Cancel menu input
# <u_key>					Up: Previous node
# <TAB_Key>					Show subtopic(s)
# <f_key>					Follow cross  referrence
# <l_key>					Revisits the last node in node history
# 
# Indexes
# <i_key>					Show indices
#
```

* man
```sh
# man: Online system manual (manual) divided into section
# apropos: Search manual pages names and descriptions (man -k [options] [regex]) with keyword
# whatis: Display one-line manual page description (man -f [options])

# man [section] [options] ...
#
```

## USER|GROUP MANAGEMENT

* Add User
```sh
# useradd - Low-level builtin utility with limited capabilities
$ sudo useradd new_user 	# Add new user. Account is locked by default
$ sudo useradd -U -m user   # Add new user with home DIR and primary group with the same username.
$ sudo passwd user 			# Create encrypted password for user
$ sudo usermod -U user 		# Unlock user account
```

## TEXT TOOLS & TEXT EDITORS

* grep
```sh
# Prints line(s) that matches an expression|pattern from a file or input stream
$ grep "expression" [path/to/file]		# Basic form
$ grep "root" /etc/passwd				# Prints lines that contains the word root in the /etc/passwd file

# Patterns can matched against multiple files or globbed filename
$ grep "root" /etc/*					# Checks every file in /etc/ that contains the word root
$ grep -R [search_term]					# Like above but follows symbolic links

# Important options:
$ grep -e								# Specify multiple patterns or pattern begins with a dash (-)
$ grep -i								# (case-insensitive match),
$ grep -v 								# (invert match: returns lines that do not match search pattern)
$ grep -[A|B|C] N PATTERN FILES			# Select N lines after/before/around pattern in filename(s)
$ grep -o 								# Print only matching line(s) with each on separate line.

# Extended grep: Understands pattern(s) in regular expressions
$ grep -E "regularExpression"			# egrep "regular_expression"
```

* cut

* diff
```sh
# Shows the difference between text files line by line
$ diff [Args] file1 file2				# Simple form

```

* vimdiff

* vi|vim

## FIND AND SEARCHING FILES

* find
```sh
# find [PATH] -type [TYPE] -name [NAME] -print0 	# Simple find synopsis
# PATH defaults to current directory if not specified
# 
$ find 
```

## PROCESS, MEMORY MANAGEMENT & DISK TOOLS

* Process Management: Process is a running program. Each process has Process ID (PID).
```sh
# Listing Process
$ ps 					# Quick list (snapshot) of running process for current $USER
#
## BSD OPTIONS
# Must NOT be preceeded by dash and can be grouped together
$ ps x 					# Show all your running process
$ ps ux 				# same as above but include username field

$ ps ax 				# Show all process running on the system
$ ps axu
# 
## UNIX OPTIONS
# Must preceeded by single dash (-) and can be grouped
$ ps -[e|A] 			# Show all processes 
$ ps -U USER -G			# Show all processes for USER [-G group]
$ ps -C CMD 			# Show process with command name CMD
#
## GNU LONG OPTIONS
# Preceeded by double dash (--)
#
#
```

* Memory Management
```sh
$ free [switch(es)]		# Check available memory; options: -w(ide), -h(uman readable), -s(econds delay)
$
```

* Disk Management
```sh
# Filesystems
# Mount/Unmount Disk
# Check Disk Usage
$ df -lk h 					# Display mount storage

```

## NETWORK 


## MISCELLANIA: PATH TO ENLIGHTENMENT
- lynx
- wget|aria2|curl
- od
- objdump
- hexdump
- git