#  BASH TIPS FOR ADMINS

## Directory Stack (pushd, popd, dirs)
```sh
# pushd DIR - Adds DIR to the top of the directory stack
$ pushd DIR 
$ pushd [+|-]N 		# Go to the Nth entry in the stack starting from top/bottom
$ pushd -n DIR 	    # Rotate the stack, put DIR on the directory stack but DO NOT change to DIR.

# dirs - List the directory stack
$ dirs [-p|-v] 		# List entries one per line and/or with indexes
$ dirs [-|+]N 		# List the Nth entry in the stack starting from top/bottom
$ dirs -l -v 		# List entries with indexes one per line and with full path
$ dirs -c 			# Clear the directory stack

# popd 				# Removes entries from the directory stack
$ popd [-|+]N 		# Removes the Nth entry from the stack starting from top/bottom.
$ popd -n N 		# Suppress normal behaviour: DO NOT change directory when popping Nth stack item.
```

## ReRun/Print Previous Commands
* `!!` - Rerun last command.
* `!#` - Rerun a command from History, !history_number
* `!*` - Rerun the last command that starts with * , Eg. !pu rerun the cmd that start with pu.
* `!*:p` - Print the last command that start with * , Eg. !ss:p prints the last cmd that starts with _ss._
* `!#:p` - Print the command at number from history, Eg. !12:p prints the 12th command from history.

## Re-Use Previous Command argument(s)
`cmd !$` - Run cmd with the last arg or previous command, Eg. vi !$ runs vi with last arg of previous cmd
`cmd !^` - Run cmd with the first arg of previous command, Eg. vi $^ runs vi the first arg of previous cmd
`cmd !*` - Run cmd with all the previous arg(s) of command, Eg. echo $* run echo with all the args of previous cmd
`cmd:#[-#]` - Select argument number of a command or range of args of command.
`^text^subs` - Substitute the first argument of a command, Eg. ping googl.com; ^googl^google

## Environmental Variables

* History Control
`HISTCONTROL=ignorespace` shell variable ignore commands that starts with space (Bash Incognito Mode).

## Reverse Search Mode
`C-r` - Control R; search bash history 
`C-g` - Exit Reverse search 

## Shredding File(s) & Directories

## System Statistics (Process, Memory & Storage)
```sh
$ sudo slabtop			Displays kernel slap cache information
$ vmstat				Report virtual memory statistics
$ stat filename			Report file/filesystem (-f) statistics
```
