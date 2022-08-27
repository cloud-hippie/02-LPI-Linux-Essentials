# 4.3 - WHere Data is Stored

Everything in etc is configuration related

System Boot COnfiguration - /boot
- Contains boot loader ocnfigration files and parameters, Linux kernel, and initial RAM disk

Partition Mount Points - /etc/fstab
- Contains a list of Partiions to mount automatically and where they live within the file system.

User Attributes - /etc/passwd
- Constains a list of local users and their attributes.

Groups - /etc/group
- Contains aList of local users and attributes

Host Files - /etc/hosts
- Contains a list fo IP addressed and the hostname we want the system to associate with them.

`sysfs` - all RAM

## Processes

ps - snapshot of all the current processes

`/proc/<PID>` - Process data is stoed in the `/proc/` within individual `pid` folders.

`ps aux` - BSD based list all processes
`ps -eF` - Linux all processes

`/sys` - provides system information regarding attached hardware

`/dev` - Contains all device files.


# System Messaging

Kernel Ring Buffer - holds messages related to the operation of the kernel.
- Simply a buffer for consistent data.

## Logging

System Logging Protocol - syslog, rsyslog
- Syslog isa service that performs log message collection

Common Logs

/var/log/messages - General system log and messages
/var/log/syslog - Logging for Debian based systems.

/var/log/auth.log - Authentication logs
/var/log/secure - For RedHat based system

/var/log/boot.log - System boot logs
/var/log/cron.log - Cron job logs
/var/log/kern.log - Kernel logs
/var/log/faillog - Authentication Fail Logs

# 4.4 - Networking

Switch - forwarding information to devices on the same network

DNS Client Config - The basics of DNS and Client configration.

DNS - Domain Name System
- Maps the domain name to their respective IP address.

```bash
dig www.linuxacademy.com
```

/etc/resolv.conf - configrationfile used to determine whic hto used for DNS queries.

/etc/hosts - used for statically mapping ips to hostnames.



# Host Computer on the Network

`ip route show` - show the current routing table
`ip addr show` - show the current addresses

`ifconfig` - view and change the interface configration

`netstat` and `ss` - view listing sevices and active connections.
