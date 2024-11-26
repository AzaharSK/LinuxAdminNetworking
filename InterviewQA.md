### Basic Linux Questions
* What are the key differences between Linux and Unix?
* Explain the Linux boot process.
* How do you check disk usage and available disk space? Commands: df, du.
* How do you find a specific process and kill it? Commands: ps, top, kill, killall.
* How do you list all running services on a Linux system? Commands: systemctl, service.

### File and Directory Management
* What command would you use to find a file by name in a directory? Command: find.
* How do you recursively search for a specific string in files? Command: grep -r.
* What is the difference between cp, mv, and rsync?
* How do you create, extract, and compress files using tar, gzip, or zip?
* What are hard links and soft links? How do you create them? Command: ln.

### Permissions and Security
* How do file permissions work in Linux?
* What does chmod 755 mean?
* How do you change ownership of a file or directory? Command: chown.
* What is the difference between sudo and su?
* Explain Linux capabilities like SELinux or AppArmor.
* How would you secure SSH access to a Linux server?
* Examples: Key-based authentication, disabling root login, changing default port.

### Networking
* How do you check network connectivity on a Linux server?
* Commands: ping, curl, wget.
* What does netstat or ss command do?
* How do you list open ports and their associated processes?
* Commands: netstat -tuln, ss -tuln.
* How do you configure a static IP address in Linux?
* What is iptables or firewalld? How do you use them?

### Processes and Performance
* What is the difference between cron and at?
* How do you monitor resource usage (CPU, memory, disk, network)? Tools: top, htop, vmstat, iostat.
* How do you troubleshoot a high CPU usage issue on a Linux server?
* How do you view logs in Linux? Command: tail -f, journalctl, /var/log.

### Storage and File Systems
* What is the difference between ext4, XFS, and NTFS file systems?
* How do you mount a filesystem in Linux?
* How do you check and repair a corrupted file system? Commands: fsck, e2fsck.
* How do you create and manage LVM (Logical Volume Manager)?
* What is RAID? How would you configure RAID in Linux?

### Cloud and Virtualization
* What is the difference between a VM and a container?
* How do you manage containers on Linux? Tools: Docker, Podman, Kubernetes.
* What is the purpose of cloud-init in cloud instances?
* How would you configure a Linux server to use dynamic DNS in a cloud environment?
* How do you use SSH to connect to cloud servers without a password?

### Scripting and Automation
* How do you write a simple shell script to monitor disk usage?
* Explain the difference between bash, sh, and zsh.
* How do you schedule jobs using crontab?
* How do you pass parameters to a shell script?
* What is the significance of #!/bin/bash in a script?
* Advanced and Cloud-Specific
* What is a bastion host, and how would you configure it in Linux?
* How do you troubleshoot boot issues in a Linux server?
* How do you securely transfer large files between servers? Tools: scp, rsync, sftp.
* How do you set up NFS or Samba in Linux for file sharing?
* What tools do you use to monitor Linux servers in a cloud environment? Examples: Prometheus, Grafana, CloudWatch, Nagios.
* Cloud-Integrated Linux Concepts
* How would you resize a cloud-based Linux instance's disk volume without downtime?
* Explain the process of attaching and mounting an EBS volume in AWS to a Linux instance.
* How do you use Ansible or Terraform to manage Linux instances in the cloud?
* What are the key differences between user-data scripts and cloud-init in cloud servers?
* How do you handle log aggregation from Linux servers in a cloud environment?

### Troubleshooting Scenarios
* A server is unreachable via SSH. How would you troubleshoot it?
* How do you debug a server with high memory usage?
* What steps would you take to restore a corrupted bootloader (GRUB)?
* A process is stuck and not responding to kill. What would you do?
* How do you identify and resolve DNS resolution issues on a Linux server?
* Behavioral/Scenario-Based Questions
* Explain a challenging problem you solved on a Linux server in a cloud environment.
* How do you approach automating Linux server management tasks?
* How do you handle scaling issues in a cloud-based Linux application?
* Describe your experience with CI/CD pipelines involving Linux.
* What’s your strategy for ensuring Linux server security in a cloud environment?

### Tips for Preparation:
* Practice common commands (find, grep, sed, awk, etc.).
* Familiarize yourself with cloud integration tools like Ansible, Terraform, and cloud provider CLI tools.
* Learn containerization basics (Docker, Kubernetes).
* Understand Linux networking and troubleshooting in cloud environments.
* Be ready to explain real-world use cases and your experiences with Linux in cloud systems.
