# Basic Terminal
## Date and Time Configuration
Display current date and time
1. date command
```bash
$ date # prints current date and time to terminal
```
2. datetimectl command (prints date and time in more details)
```bash
$ datetimectl
```
* More information can found in ```man date, man timedatectl```

3. System wide locale settings.
config file **/etc/locale.conf** is read during early boot stage by systemd daemon.
All services on the system inherits this config.
Service or user config can override the system wide locale config.

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
* Read more from the man page ```man localectl```
