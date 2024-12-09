### USER DETAILS
The id command in Linux displays a user's UID (User ID), GID (Group ID), and the groups they belong to. This is particularly helpful for understanding a user's permissions and group memberships.

```bash
mistu@ubuntu:~$ id
uid=1000(mistu) gid=1000(mistu) groups=1000(mistu),4(adm),24(cdrom),27(sudo),30(dip),46(plugdev),120(lpadmin),132(lxd),133(sambashare)
```

### **User Details**

| **Command**         | **Description**                                                                     |
|---------------------|-------------------------------------------------------------------------------------|
| `cat /etc/passwd`   | View all user details (username, UID, GID, shell, etc.) from `/etc/passwd`.           |
| `cat /etc/shadow`   | View all encrypted passwords and password policies (requires root access).           |
| `cat /etc/group`    | View all groups and user memberships.                                                |
| `cat /etc/gshadow`  | View encrypted group passwords & policies (requires root access).                    |
| `id username`       | View user UID, GID, and groups.                                                      |
| `whoami`            | Show current logged-in user.                                                        |
| `groups username`   | List all groups a user belongs to.                                                   |
| `finger username`   | Show user details (name, shell, etc.).                                               |

![Screenshot from 2024-12-08 01-14-51](https://github.com/user-attachments/assets/136c6b30-e26f-4ef0-9dae-08356bd8488e)

### Hostname or Machine name

```bash
$hostname 
node1.ibm.com 
```
* node1 => server name
* ibm.com => domain name


### `hostname` Command Options

# `hostname` Command Options

| **Option**     | **Description**                                              | **Sample Output**                    |
|----------------|--------------------------------------------------------------|--------------------------------------|
| `hostname -a`  | Displays the **alias names** of the host.                     | `webserver1 myserver`               |
| `hostname -A`  | Displays the **Fully Qualified Domain Name (FQDN)**.          | `webserver1.example.com`            |
| `hostname -b`  | **Boot** the system with the name from `/etc/hostname`.        | (No output, this affects booting)   |
| `hostname -d`  | Shows the **DNS domain name** of the host.                    | `example.com`                       |
| `hostname -f`  | Displays the **fully qualified domain name (FQDN)**.          | `webserver1.example.com`            |
| `hostname -F`  | Sets the hostname from the specified file (e.g., `/etc/hostname`). | (No output, sets hostname)         |
| `hostname -i`  | Shows the **IP address** of the host.                         | `192.168.1.10`                      |
| `hostname -I`  | Shows all network **IP addresses** assigned to the host.      | `192.168.1.10 192.168.1.20`         |
| `hostname -s`  | Displays the **short hostname** (only the first part of FQDN).| `webserver1`                        |
| `hostname -y`  | Displays the **NIS/YP domain name**.                          | `example`                           |
| `hostname --help` | Displays help information.                                  | (Shows usage details and options)   |
| `hostname --version` | Shows the version of the `hostname` command.              | `hostname from util-linux 2.36`     |



### Switch USER
```bash
$su - username1 
$su - root
```
* -  => Load the env of the user "root"
* root => argument: root user

#### Root access : when you do not know root password:
$ sudo -s user1
password: <password for user1>
root@machine# 

### LogOut

```bash
#CTRL + D
#exit
#logout
```

### Environment variable:

```bash
mistu@ubuntu:~$ env
SHELL=/bin/bash
SESSION_MANAGER=local/ubuntu:@/tmp/.ICE-unix/4142,unix/ubuntu:/tmp/.ICE-unix/4142
QT_ACCESSIBILITY=1
COLORTERM=truecolor
XDG_CONFIG_DIRS=/etc/xdg/xdg-ubuntu:/etc/xdg
SSH_AGENT_LAUNCHER=gnome-keyring
XDG_MENU_PREFIX=gnome-
GNOME_DESKTOP_SESSION_ID=this-is-deprecated
LANGUAGE=en_IN:en
GNOME_SHELL_SESSION_MODE=ubuntu
SSH_AUTH_SOCK=/run/user/1000/keyring/ssh
XMODIFIERS=@im=ibus
DESKTOP_SESSION=ubuntu
GTK_MODULES=gail:atk-bridge
PWD=/home/mistu
LOGNAME=mistu
XDG_SESSION_DESKTOP=ubuntu
XDG_SESSION_TYPE=wayland
SYSTEMD_EXEC_PID=4170
XAUTHORITY=/run/user/1000/.mutter-Xwaylandauth.W4XVX2
HOME=/home/mistu
USERNAME=mistu
IM_CONFIG_PHASE=1
LANG=en_IN

XDG_CURRENT_DESKTOP=ubuntu:GNOME
VTE_VERSION=6800
WAYLAND_DISPLAY=wayland-0
GNOME_TERMINAL_SCREEN=/org/gnome/Terminal/screen/306a64a3_48f8_4aba_b956_38fb34b7fb25
GNOME_SETUP_DISPLAY=:1
LESSCLOSE=/usr/bin/lesspipe %s %s
XDG_SESSION_CLASS=user
TERM=xterm-256color
LESSOPEN=| /usr/bin/lesspipe %s
USER=mistu
GNOME_TERMINAL_SERVICE=:1.205
DISPLAY=:0
SHLVL=1
QT_IM_MODULE=ibus
XDG_RUNTIME_DIR=/run/user/1000
XDG_DATA_DIRS=/usr/share/ubuntu:/usr/local/share/:/usr/share/:/var/lib/snapd/desktop
PATH=/home/mistu/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin:/snap/bin
GDMSESSION=ubuntu
DBUS_SESSION_BUS_ADDRESS=unix:path=/run/user/1000/bus
_=/usr/bin/env
```

# Linux User Management Commands

| **Command**     | **Options**                  | **Description**                                 | **Example**                      | **Example Output**                        |
|-----------------|-----------------------------|-------------------------------------------------|-----------------------------------|-------------------------------------------|
| `whoami`        | None                         | Displays the current logged-in username.       | `whoami`                          | `john_doe`                                |
| `id`            | `-u, -g, -G, -n`             | Displays user ID (UID) and group information.  | `id`                              | `uid=1000(john_doe) gid=1000(john_doe) groups=1000(john_doe),27(sudo)` |
| `adduser`       | `[username]`                 | Creates a new user with a home directory.      | `sudo adduser alice`              | `Adding user 'alice'...`                  |
| `useradd`       | `-m, -d, -s, -c, -e`         | Adds a new user (less interactive than adduser). | `sudo useradd -m -s /bin/bash bob`| No output if successful                   |
| `passwd`        | `[username]`                 | Sets or changes the password for a user.      | `sudo passwd alice`               | `Enter new password: ********`            |
| `usermod`       | `-aG, -L, -U, -s, -d, -e`    | Modifies user account properties.             | `sudo usermod -aG sudo alice`     | No output if successful                   |
| `deluser`       | `[username]`                 | Deletes a user and optionally removes files.  | `sudo deluser alice`              | `Removing user 'alice'...`                |
| `userdel`       | `-r`                         | Deletes a user and removes their home directory. | `sudo userdel -r bob`            | No output if successful                   |
| `chage`         | `-l, -M, -m, -W, -I`         | Configures password expiry policies.          | `sudo chage -l john_doe`          | `Last password change: Aug 19, 2024`      |
| `groups`        | `[username]`                 | Displays groups the user belongs to.          | `groups john_doe`                 | `john_doe : john_doe sudo`                |
| `finger`        | `[username]`                 | Displays detailed information about a user.  | `finger john_doe`                 | `Login: john_doe Name: John Doe Directory: /home/john_doe` |
| `getent`        | `passwd [username]`          | Queries user info from the system database.   | `getent passwd john_doe`          | `john_doe:x:1000:1000:John Doe:/home/john_doe:/bin/bash` |
| `su`            | `[username]`                 | Switches to another user account.             | `su - alice`                      | `alice@hostname:/home/alice$`             |
| `sudo`          | `[command]`                  | Executes a command with elevated privileges. | `sudo apt update`                 | Updates system package lists             |
| `w`             | None                         | Displays users currently logged in.           | `w`                               | Shows logged-in users and active sessions |
| `who`           | None                         | Shows who is logged in.                        | `who`                             | `john_doe :0 2024-08-19 08:12 (:0)`        |
| `last`          | `[username]`                 | Displays login history of users.              | `last john_doe`                   | `john_doe tty7 :0 Fri Aug 18 08:21 - down` |
| `lastlog`       | None                         | Shows the last login of all users.             | `lastlog`                         | Displays last login for each user         |
| `logname`       | None                         | Prints the current logged-in user.            | `logname`                         | `john_doe`                                |
| `whoami`        | None                         | Displays the current user's name.             | `whoami`                          | `john_doe`                                |
| `pinky`         | `[username]`                 | Displays concise user information.            | `pinky john_doe`                  | Similar to `finger` but more concise.     |

---

### Notes:
- **Commands like `useradd` and `userdel`** require `sudo` privileges.
- **Interactive commands like `passwd`** require user input for passwords.
- **Difference between `adduser` and `useradd`**: `adduser` is more user-friendly, while `useradd` is lower-level and requires manual directory and file setup.
- **Password expiration commands**: `chage` can be used to set when a password expires, how soon a warning is issued, etc.



# Linux Password Management Commands

| **Command**                        |  **Description**                                                         |  **Example Usage**                    |  **Example Output**                                                                                             |
|------------------------------------|-------------------------------------------------------------------------|--------------------------------------|----------------------------------------------------------------------------------------------------------------|
| `passwd`                           |  Allows the user to change their own password.                            |  `passwd`                            |  ```Changing password for user john_doe. Current password: **** New password: ******** Retype new password: ******** passwd: all authentication tokens updated successfully.```  |
| `sudo passwd username`             |  Lets an administrator set or change another user's password.             |  `sudo passwd alice`                 |  ```Enter new UNIX password: ******** Retype new UNIX password: ******** passwd: password updated successfully.```  |
| `sudo chage -l username`           |  Shows the password expiry policy, last change date, and expiration rules.|  `sudo chage -l alice`               |  ```Last password change: Aug 19, 2024 Password expires: never Password inactive: never Account expires: never Minimum number of days between password change: 0 Maximum number of days between password change: 99999 Number of days of warning before password expires: 7```  |
| `sudo chage -d 0 username`         |  Force the user to change their password on next login.                   |  `sudo chage -d 0 alice`             |  No output, but forces the user to change their password at next login.                                          |
| `sudo passwd -l username`          |  Lock the user’s password (i.e., disable login).                          |  `sudo passwd -l alice`              |  ```passwd: password expiry information changed.```                                                             |
| `sudo passwd -u username`          |  Unlocks a previously locked user's password.                             |  `sudo passwd -u alice`              |  ```passwd: password expiry information changed.```                                                             |



## Usermanagement demo


### Create a new user whose full name is “Ying Yang,” with the login name
(account name) of yyang. Type the following:
```bash
[root@server ~]# useradd -c "Azaharuddin Sk" azahar
```
This command will create a new user account called yyang. The user will be
created with the usual Fedora default attributes. The entry in the /etc/passwd
file will be
```
azahar:x:1001:1001:Azaharuddin azahar:/home/azahar:/bin/bash
```
* The UID number is the same as the GID number. The value is 1001 in
this example.
* The default shell for new users is the bash shell (/bin/bash).
* A home directory is automatically created for all new users (for
example, /home/azahar).

### Verify the user "azahar"
```bash
[root@server ~]# id azahar
uid=1001(azahar) gid=1001(azahar) groups=1001(azahar)
```
### Examine the entry for "azahar" in the /etc/passwd file

```bash
root@server ~]# grep azahar /etc/passwd
azahar:x:1001:1001:,,,:/home/azahar:/bin/bash
```
### Change the password
```bash
[root@server ~]# passwd azahar
Changing password for user azahar.
New password: xxxxx
Retype new password:xxxxx
passwd: all authentication tokens updated successfully.
```
* Password Tips:  A good technique might be to choose a phrase and then pick the first letter of every
word in the phrase. Thus, the phrase “coffee is VERY GOOD for you and me” becomes ciVG4yam.
The phrase is memorable, even if the resulting password isn’t.

### Create a new group called R&D:
```bash
[root@server ~]# groupadd R&D
```
### Examine the entry for the research group in the /etc/group file:
```bash
[root@server ~]# grep 'R&D' /etc/group
R&D:x:1002:
```
### Change the GID of the "R&D" group to 1050
```bash
[root@server ~]# groupmod -g 1050 'R&D'
[root@server ~]# grep 'R&D' /etc/group
R&D:x:1050:
```
