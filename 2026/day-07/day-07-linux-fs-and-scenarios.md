✅ Day 07 – Linux File System Hierarchy & Scenario-Based Practice

🗂️ Part 1 – Linux File System Hierarchy
/ (Root Directory)

Starting point of the entire Linux filesystem.

ls -l /

 bin, etc, home, var, usr

I would use this when:
I need to explore the system from top level.

/home

Home directories for normal users.

ls -l /home


Observed: ubuntu, user

I would use this when:
Managing user files and scripts.
/root

Home directory of root user.

ls -l /root


I would use this when:
Logged in as root and need admin scripts.

/etc

Configuration files for system and services.

ls -l /etc | head


Observed: hostname, hosts, ssh

I would use this when:
Editing config files.

/var/log

System and service logs.

ls -l /var/log


Observed: syslog, auth.log

I would use this when:
Troubleshooting issues.

/tmp

Temporary files.

ls -l /tmp


I would use this when:
Testing or temporary storage.

/bin

Essential system commands.

ls -l /bin | head


Observed: ls, cp, mv

/usr/bin

User-level commands.

ls -l /usr/bin | head


Observed: git, python

/opt

Optional third-party software.

ls -l /opt


Observed: empty

🔹 Hands-on Tasks
du -sh /var/log/* 2>/dev/null | sort -h | tail -5
cat /etc/hostname
ls -la ~


Observation:
Largest log directories and hostname displayed.



🧪 Part 2 – Scenario-Based Practice
✅ Scenario 1: Service Not Starting

Step 1

<!-- check the status -->
systemctl status myapp  


Why: Check if failed or stopped.

Step 2
<!-- view log for 50 -->
journalctl -u myapp -n 50


Why: View error logs.

Step 3

systemctl is-enabled myapp


Why: Check if starts on boot.

Step 4

systemctl start myapp


Why: Try starting service.

✅ Scenario 2: High CPU Usage

Step 1

top


Why: See live CPU usage.

Step 2

ps aux --sort=-%cpu | head -10


Why: Find top CPU-consuming process.

Step 3

kill PID


Why: Stop bad process if required.

✅ Scenario 3: Finding Docker Logs

Step 1

systemctl status docker


Why: Confirm service running.

Step 2

journalctl -u docker -n 50


Why: View recent logs.

Step 3

journalctl -u docker -f


Why: Follow logs live.

✅ Scenario 4: Permission Denied Script

Step 1

ls -l /home/user/backup.sh


Why: Check permissions.

Step 2

chmod +x /home/user/backup.sh


Why: Add execute permission.

Step 3

./backup.sh


Why: Run script.

🧠 What I Learned

Logs live in /var/log

Configs live in /etc

Always check status → logs → permissions