# Summary

**Linux Server:** `Baker_Street_Linux_Server 5.15.0`

- Backed up the server  
- Removed unnecessary accounts and groups, locked inactive users, and deleted their files  
- Enforced password policy; set passwords for 2 user accounts without passwords  
- Audited `sudoers` file  
- Audited world-writable files and incorrect ownership settings  
- Audited and secured SSH (note: could not get the service to start)  
- Updated outdated packages and unpatched vulnerabilities  
- Disabled unnecessary services  
- Enabled configuration logging  
- Created scripts to automate all of this  
- Scheduled the scripts to run using `crontab`  
