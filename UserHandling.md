### USER DETAILS
The id command in Linux displays a user's UID (User ID), GID (Group ID), and the groups they belong to. This is particularly helpful for understanding a user's permissions and group memberships.

```bash
mistu@ubuntu:~$ id
uid=1000(mistu) gid=1000(mistu) groups=1000(mistu),4(adm),24(cdrom),27(sudo),30(dip),46(plugdev),120(lpadmin),132(lxd),133(sambashare)
```
### Hostname or Machine name

```bash
$hostname 
node1.ibm.com 
```
* node1 => server name
* ibm.com => domain name


### `hostname` Command Options

| **Option**   | **Description**                                             | **Example**                     |
|--------------|-------------------------------------------------------------|-----------------------------------|
| `-a`         | Displays the **alias names** of the host.                     | `hostname -a`                    |
| `-A`         | Displays the **FQDN (Fully Qualified Domain Names)**.         | `hostname -A`                    |
| `-b`         | **Boot** the system with the name from `/etc/hostname`.       | `hostname -b`                    |
| `-d`         | Shows the **DNS domain name** of the host.                    | `hostname -d`                    |
| `-f`         | Displays the **fully qualified domain name (FQDN)**.          | `hostname -f`                    |
| `-F FILE`    | Sets the hostname from the specified file (e.g., `/etc/hostname`). | `hostname -F /etc/hostname`      |
| `-i`         | Shows the **IP address** of the host.                         | `hostname -i`                    |
| `-I`         | Shows all network **IP addresses** assigned to the host.      | `hostname -I`                    |
| `-s`         | Displays the **short hostname** (only the first part of FQDN).| `hostname -s`                    |
| `-y`         | Displays the **NIS/YP domain name**.                          | `hostname -y`                    |
| `--help`     | Displays help information.                                    | `hostname --help`                |
| `--version`  | Shows the version of the `hostname` command.                  | `hostname --version`             |


### Switch USER
```bash
$su - username1 
$su - root
```
* -  => Load the env of the user "root"
* root => argument: root user

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

