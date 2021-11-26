# Basic Commands
Navigating the filesystem, create files/directories, searching files and info on commands.

## Navigating the filesystem
`ls` - displays list of files/directories the current working directory (folder). Hidden files/directories are not shown by default. Given `ls` some options/arguments changes its' behavior. Options are usually preceeded by a -. Example: `ls -a`, `ls -l`.
`dir` -   Similar to ls

`ls` - Lists contents of a directory excluding hidden files
`ls -a` - Lists all content of a directory including hidden files/directories
`ls -l` - Lists contents of a directory excluding hidden files/directory

You can specify a directory you want its' contents to be listed.
`ls /etc` - Lists the contents of /etc directory
`ls -lh /home` - Lists the contents of /home in a listing format with human readable size information.

`cd` - Use this command to change/move from the working directory. Typing just `cd` and pressing enter changes you to $HOME directory. The `cd` command takes some few arguments. More info at `help cd` on the command line.

`cd` - Changes current working directory to $HOME
`cd /etc` - Changes working directory to `/etc`.

[*] Type `pwd` and press enter to know your current working directory.


### Summary
The shell provides mechanism to navigate the command line. `cd` to change directory, `ls` to list contents of a directory and `pwd` to know the current working directory.
Read more from the manuals and help infos.
`man ls` - manpages for ls
`help cd` - Help for cd shell builtin.
`help pwd` - help for pwd shell builtin.

