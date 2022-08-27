# Security within Linux

Standard User accounts - limited permissions
- View system configuration
- No permissions to modify system configuration.
- Given permissions to modify using the word `sudo` 

`sudo` - Super-User DO
- Provides the mechanism whereby a user account is permitted the ability to run a command with Elevated permissions.

Root - The administrative account for the SYSTEM
- FULL access to all the permissions on the system
- System Level administration 
- A more seacure management would be to be diligent with `sudo` use.

`/etc/passwd` - this file contains the following 7 sttributes for each local user
- Username
- Password 
- UserID
- GroupID
- GECOS - Long Name
- HomeDirectory - Login Directory
- Login Shell - Log in interpretor

`/etc/shadow` - contains actual passwords for each local user in an encrypted form. 
- Username
- PAssword
- LastChanges - days since password change
- Minimum - minimum number of days between password changes
- Maximum - maximum number of days between password changes
- Warn - Number of Days before password expiration to warn user
- Inactive - Number of days since expieration
- Expire - absolute expiration date.

`/etc/group` - The file contains group membership for all local system users and contains the following.
- Group - unique group name
- Password
- GroupID
- GroupList


`groups user` - shows the groups the user belongs to
`getent USER` - show; the entities of a given user.



## System Users

Application Service Accounts
- Syste musers are generally deployed when applications are installed.
- Their home directories are set to application forlders and they normally do not have a login shell
- Used to separate functional privleges from other applications and Services.


# Groups

useradd [options] username - Used to add or create users. Options are available for specifying the UIS, GID, gome directory and group membership.


`/etc/skel` - Boilerplate files and folders for new accounts.
- Automatically copies when a newt users home directory is Created via then useradd utility.

passwd [username] - update a users password
- Used to update then current users password or another user's with another's sufficient privleges.

groupadd [options] groupane
- Create a new group

# User IDs

Numeric ID - All logical users are given an identification number that is sotred along with the corresponding username in `/etc/passwd` 

`UID 0` - ALWAYS the root user
`UID 1-99` - Traditionally reserved for system users
`UID 1000+` - Standard users. 
`UID 65534` - Reserved for the user NOBODY

Remote Users - a range of UIDs reserved for non-local users in order to prvent UID collisions with local users.

`sudo usermod -a -G management jenn` - Modify the user jenn and add her to the non-primary group management.

`-a` - append
    
`id USER` - Get the informaiton for the given user


# Files and Permissions

Numeric Permissions
7 - Read Wrtite Execute
6 - Read Write
5 - Read Execute
4 - Read
3 - Execute write
2 - Write
1 - Execute
0 - No permissions

```
drwxr-xr-x  4 justinrice  staff   128 Jan 29 19:46 .vagrant
```
is_directory-user-group-everyone

`chown` - Change the ownership of the given file or diretory
`chown [options] USER:GROUP FILE`

`chmod` - CHange the permissiosn of the file


# Using Temporary Files and Directories

`/tmp` - All content in `/tmp` is cleared upon system boot. The directory is used by programs or Scrips that require temporary files or directories.

`/var/tmp` - All content persissts through a system boot
- PERSISTS past boot

`mktemp` - Create temporary file or directory
Used to create adhoc files and directories with randomezied file name portion.



# Symbolix Links

Symbolic Links - Create a symbolix Link to a file or directory 

`ln -s [TARGET] [LINK NAME]` 