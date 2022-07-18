#  BASH TIPS FOR ADMINS

## Navigating Filesystems
`pushd`
`popd`

## ReRun/Print Previous Commands
* `!!` - Rerun last command.
* `!#` - Rerun a command from History, !history_number
* `!*` - Rerun the last command that starts with * , Eg. !pu rerun the cmd that start with pu.
* `!*:p` - Print the last command that start with * , Eg. !ss:p prints the last cmd that starts with _ss._
* `!#:p` - Print the command at number from history, Eg. !12:p prints the 12th command from history.

## Re-Use Previous Command argument(s)
`cmd !$` - Run cmd with the last arg or previous command, Eg. vi $! runs vi with last arg of previous cmd
`cmd !^` - Run cmd with the first arg of previous command, Eg. vi $^ runs vi the first arg of previous cmd
`cmd !*` - Run cmd with all the previous arg(s) of command, Eg. echo $* run echo with all the args of previous cmd
`cmd:#[-#]` - Select argument number of a command or range of args of command.
`^text^subs` - Substitute the first argument of a command, Eg. ping googl.com; ^googl^google

## History Control
`HISTCONTROL=ignorespace` shell variable ignore commands that starts with space (Bash Incognito Mode).

## Reverse Search Mode
`C-r` - Control R; search bash history 
`C-g` - Exit Reverse search 