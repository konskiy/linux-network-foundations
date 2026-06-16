# Linux Basics Notes (Days 8-12)

## Filesystem
/      - root, the top of the whole filesystem, everything else is inside it
/home  - personal folders for each user (documents, files)
/etc   - configuration files for the whole system and programs
/var   - files that change while the system is running (logs, caches, mail)
/tmp   - temporary files, safe to delete, not critical
/usr   - installed programs and their files (not personal settings)

## Users & Groups
- Each user is a separate identity in the system with their own permissions
- Groups give the same permissions to several users at once
- whoami - shows which user you are currently working as
- id - shows your UID (user number) and the groups you belong to
- sudo adduser - creates a new user (requires admin rights)
- sudo - temporarily gives root rights for one command, and logs who did it

## Permissions
- r/w/x = read / write / execute - rights to read, write, or run a file
- Permissions are split into 3 levels: owner, group, others
- chmod - changes file permissions (e.g. chmod +x makes a file executable)
- chown - changes the owner and/or group of a file
- Dangerous: if a file with passwords/configs is writable by "others"

## Processes & Services
- ps aux - shows all running processes (CPU, MEM, PID, etc.)
- A process is any program running right now, it has its own PID
- A service is a process that runs in the background all the time (e.g. SSH, a web server)
- systemctl - command to manage services (start/stop/restart/status/enable)
- A suspicious process that isn't a known service can be a sign of malware

## Logs
- Logs are records of system events (logins, errors, services starting)
- journalctl - shows logs from the systemd journal (centralized log storage)
- journalctl -xe - shows the latest entries with extra explanation of what went wrong
- /var/log - folder with classic log files (e.g. auth.log)
- auth.log - records login attempts, important when investigating a breach