# --[ INTRODUCTION - WINDOWS POWERSHELL

* Task automation solution
* Cross platform
* Command-line shell
	- Accepts and returns objects
	- Supports Tab-completion & Command-line History
	- Pipeline for chaining command-lets
	- In-console help system
* Scripting language
	- Built on Common Language Runtime (CLR)
	- All I/O are .NET objects
	- Extensible through functions, scripts, class & modules
	- Builtin support for common data types (CSV, JSON, XML)
	- Formatting for easy input & creating dynamic types
	- For automation & management of systems
* Configuration management framework
	- Desired State Configuration (DSC), management framework for managing enterprise infrastructure
	- Create declarative configuration and custom scripts for repetitive deployment
	- Enforces configuration settings and reports on configuration drift
	- Deploy configs using push/pull models

## START POWERSHELL
* Press WIN Key, Type powershell, Press enter
* Press WIN + R, Type powershell, Press enter
* WIN + X
* Run as admin: WIN + R, Type powershell, Press CTRL + Shift + Enter

`pwsh`

`$PSVersionTable.PSVersion` Version of powershell installed/running

## POWERSHELL COMMAND-LETS
Commands in powershell are referred to as command-lets (_cmdlets_) and are case insensitive
Any command on the system can be run in powershell
Name of a powershell command consists of **Verb-Noun** pair.
Command prompt commands in powershell are aliases to powershell cmdlets.

Builtin cmdlets helps discover available cmdlets, usage & types they operate on.

`$cmdlet [Parameter(s) ...] [Options ..]` - Syntax

`Get-Verb` Returns lists of verbs adhered by most cmdlets and description of what they do
`Get-Command` Retrieves all cmdlets installed on the system
`Get-Member` Operates on object based output, object, properties and methods available for a cmdlet
`Get-Help cmdlet` Displays a help page that describes various parts of a command-let 

**These command-lets can be used to discover almost anything about powershell.**

### Filter Verb & Noun cmdlets
`Get-Verb` Cmdlet outputs a long lists of verbs and what a each verb does. It gives an idea of what a cmdlet is trying to do.

`Get-Command` Cmdlet returns lists of available commands. Filter can be applied to response to limit outputs
				Filter can be parameters or another helper cmdlets.

`Get-Command -Name '*Process'` Queries the name property of the command
`Get-Command -Verb 'Get'` Filter on verbs. List all commands with the verbs 'Get'
`Get-Command -Noun U*` Filter on nouns
`Get-Command -Verb Get -Noun U*` Mixed filters to narrow down search results

### Filter Results using helper cmdlets
`Select-Object` cmdlet that picks specific properties from one or more objects and narrow it down with parameters.

`Get-Command | Select-Object -First 3` Selects first 3 objects of the cmdlet

`Where-Object` Selects objects from a collection based on values of properties

`Get-Process | Where-Object {$_.ProcessName -like "p*"}`
	Get-Process produces a collection of process, piped the object to Where-Object with -like paramater and wildcard to filter results.

### Exploring objects with Get-Member
The cmdlet displays the type, properties and methods of an object. 
`Get-Process | Get-Member`

Using the -MemberType parameter, results can be filtered.
`Get-Process | Get-Member -MemberType Method`

Piping the results to `Select-Object` you can select specific column(s) to display separated by comma
`Get-Process | Get-Member -MemberType Method | Select-Object Name, Definition`

### Searching By Type
`Get-Command -ParameterType Process` Output commands that operate on Parameter type

### Find Related Commands that operates on a type
`Get-Process | Get-Member | Select-Object TypeName -Unique`
`Get-Command -ParameterType Process`

### Command-let Aliases
Aliases are shortened cmdlet name
`Start-Process notepad`
`Start notepad` 

`Stop-Process notepad`
`Stop notepad`

`Get-Alias` - To see all aliases
`Get-Alias alias` - To see the full cmdlet
`get-Alias gal` - Prints the full cmdlet 

### Find Help on cmdlet
`Get-Help -Name cmdlet` - Help on cmdlet
`Help -full -Name cmdlet`	- Get a detailed help/usage on the cmdlet


### Lists of Services on the system
`Get-Service` - Lists all services
`Get-Service | Where-Object {$_.Status -eq "Status"}` - Lists all services with 'Status'
`Get-Service | Export-CSV service.csv`
`Get-Service | Select-Object Name, Status | Where-Objec {$_.Status -eq "Status" } | Export-CSV output.csv`

`Get-Process` - List all active processes 
`Get-Process procName1, procName2, ... | Format-List *` - 
`Stop-Process -Name procName -Verbose`

### Sample Powershell Commands in Real world
```ps
# List running process; Filter output remove duplicate names and Kill the process
PS Prompt> get-process | select-object ProcessName -unique | where-object ProcessName -Like "*edge" | stop-process 

```

### Formatting && Output
`Get-ChildItem | Format-List *` Detailed list view
`Get-ChildItem | Format-Wide`	- Column view
`Write-Output string`	- Print string to console
`Get-ChildItem | Out-Null`	- Discard output
`Get-ChidItem | Out-String` - Convert object to string
`Cet-ChildItem | Out-GridView` - Interactive output view & filtering # Not available on macOS
`Get-ChildItem | Out-File filename`	- Redirect output to filename
`Get-Content filename`	- Prints content of filename to console # Alias gc

### Create | Copy | Move | Rename | Delete Item/Directory
`New-Item -ItemType typeName itemName` - Create an item
`New-Item -ItemType Directory folderName` - Create folder
`md directoryName` - create a new directory
`cpi src dest # Copy-Item`	- Copy Item from source to destination
`mi src dest # Move-Item`	- Move Item from source to destination
`ren itemList # Remove` - Remove item(s)


### Event Log Cmdlets
* Get-EventLog
* Get-WinEvent

## PROFILE AND EXECUTION POLICY
`$Profile` - Profile variable: Location of powershell startup profile
`$Profile | Select-Object *` - Location all profiles


Default script execution policy is restricted unless changed

### Execution Policies
* Restricted -	Defaults, Stops script from running
* All Signed -	Will run scripts from trusted publisher
* Remote Signed - Run locally created scripts
* Unrestricted - Warn before Running scripts with no restrictions
* Bypass	- run script without warning

`Get-ExecutionPolicy -List` - Get the current execution policies
`Set-ExecutionPolicy -ExecutionPolicy Policy` - Changes the execution policy


## POWERSHELL SCRIPTING
`Start-Transcript`
### Variables
$variableName = Value
`whoami = Taufiq Gh` - Creates a variable
`Write-Host $whoami` - Displays the value of variable




























