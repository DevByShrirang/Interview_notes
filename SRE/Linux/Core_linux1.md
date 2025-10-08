Linux File System

ls, 
find- command is used for searching files and directories based on name, size, type, permission, modification time etc
      find /home -type d  --> find all directories under /homme.
      find /home -type f  --> find all regular files 
      find / -type f -size +100M  --> find files larger than +100M.
      find /var/log -type f -mtime -7 --> find files modified in last 7 days.
      find / -type f -perm 777  -->  find files with 777 permissions.

locate -  used to quickly search for files by name. faster than find bcz it doesnt search filesystem in real time.
      locate filename.txt  --> finds all paths that contain filename.txt
      locate -i report.pdf  --> finds report.pdf, REPORT.PDF, or Report.Pdf.
      locate -n 10 nginx.conf --> shows only first 10 matches.

du - Disk usage -shows how much space files/directories are using on disk. it scans the current directory and all subdirectories.
     du -h --> shows size in KB, MB,GB  instead of blocks.
     du -sh -->  shows only total size.
     du -sh * --> check usage of each file/folder inside a directory.**useful for finding which folder is eating space.**
     du -sh /var/* | sort -h -->  find biggest directories in /var

df - disk free  --> shows disk space usage and available free space on mounted filesystem.
                --> df shows disk usage of all filesystem.
     df -h --> shows size in KB, MB,GB  instead of blocks.
     df -h /var --> shows disk usage of var, shows which partition is on /var.
     df -T -->  shows filesystem type.
     df -h -x tmpfs - Exclude certain filesystem
     
/etc, /var, /home, /proc, /sys

File permissions and ownership:

chmod, chown, chgrp

umask

Symbolic vs hard links

Processes & System Monitoring

ps, top, htop

pgrep, pidof

kill, killall, pkill

nice, renice

System load (uptime, top load average interpretation)

Logs

/var/log/syslog, /var/log/messages, /var/log/dmesg

journalctl

Log rotation (logrotate)

⏰ Next 30 minutes — Networking & Security

These are heavily relevant for DevOps/SRE roles.

Networking Commands

ifconfig / ip addr

netstat, ss

ping, traceroute

curl, wget

iptables, firewalld, ufw

SSH & Connectivity

ssh, scp, rsync

SSH keys (ssh-keygen, ssh-copy-id)

scp / rsync for deployments

Security Basics

chmod for file security

sudo

User management: useradd, usermod, passwd, groups

⏰ Next 30 minutes — Scripting & Automation

Essential for DevOps/SRE efficiency.

Bash Scripting Basics

Variables, loops, conditionals

$?, $0, $1

Redirection (>, >>, <)

Pipes (|), process substitution

Common Tasks

Parsing logs (grep, awk, sed)

File search & manipulation

Monitoring via shell scripts

Example:

#!/bin/bash
LOG="/var/log/syslog"
grep "error" $LOG | tail -n 20

⏰ Last 30 minutes — Quick Commands & Scenarios

These are often asked in DevOps/SRE interviews as practical scenarios.

Quick Commands

df -h, du -sh

top, htop

free -m

uname -a, cat /proc/cpuinfo

uptime, dmesg

Scenarios to Prepare

How to check CPU/memory/disk usage.

How to check open ports and connections.

How to find which process is using a port.

How to check running services (systemctl status <service>).

How to tail logs for a service.

How to restart a service.

How to find disk space issues.

How to search logs for a keyword within a time range.

Quick Practice
Run these commands:

free -h
df -h
ps aux --sort=-%mem | head
netstat -tulnp
tail -f /var/log/syslog


This helps refresh muscle memory.

📌 Bonus Tip for Interviews

Interviewers sometimes give small Linux challenges like:

“How do you find processes using more than 50% CPU?”

“How to list top 10 largest files in a directory?”

“How to check if a port is open?”

“How to restart a failed service?”