### 1. Using Log Files
* a) ```/var/log/auth.log``` (Debian/Ubuntu) or ```/var/log/secure``` (RHEL/CentOS/Fedora)
These log files store authentication and login-related information.

### View recent login attempts:

```bash
sudo tail /var/log/auth.log      # Debian/Ubuntu
sudo tail /var/log/secure        # RHEL/CentOS
```
### Search for specific login attempts:

```bash
sudo grep 'session opened' /var/log/auth.log
sudo grep 'Failed password' /var/log/auth.log
```
* b) ```/var/log/wtmp``` and ```/var/log/btmp```
* ```wtmp``` logs all successful login records.
* ```btmp``` logs all failed login attempts.
