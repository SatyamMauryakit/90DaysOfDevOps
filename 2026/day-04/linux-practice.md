1️⃣ Check running processes

USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root           1  0.6  0.7  22272 13708 ?        Ss   18:16   0:01 /sbin/init
root           2  0.0  0.0      0     0 ?        S    18:16   0:00 [kthreadd]
root           3  0.0  0.0      0     0 ?        S    18:16   0:00 [pool_workqueue_release]
root           4  0.0  0.0      0     0 ?        I<   18:16   0:00 [kworker/R-rcu_gp]
root           5  0.0  0.0      0     0 ?        I<   18:16   0:00 [kworker/R-sync_wq]
root           6  0.0  0.0      0     0 ?        I<   18:16   0:00 [kworker/R-kvfree_rcu_reclaim]
root           7  0.0  0.0      0     0 ?        I<   18:16   0:00 [kworker/R-slub_flushwq]
root           8  0.0  0.0      0     0 ?        I<   18:16   0:00 [kworker/R-netns]
root           9  0.0  0.0      0     0 ?        I    18:16   0:00 [kworker/0:0-cgroup_destroy]

Shows all running processes

Root and system services are running

Columns include PID, CPU, MEM usage



2️⃣ Real-time process monitoring   -- top 
top - 18:21:28 up 4 min,  1 user,  load average: 0.00, 0.00, 0.00
top - 18:22:21 up 5 min,  1 user,  load average: 0.06, 0.02, 0.00
Tasks: 114 total,   1 running, 113 sleeping,   0 stopped,   0 zombie
%Cpu(s):  0.0 us,  0.2 sy,  0.0 ni, 99.8 id,  0.0 wa,  0.0 hi,  0.0 si,  
MiB Mem :   1910.7 total,   1229.4 free,    348.3 used,    496.3 buff/cac
MiB Swap:      0.0 total,      0.0 free,      0.0 used.   1562.4 avail Me

    PID USER      PR  NI    VIRT    RES    SHR S  %CPU  %MEM     TIME+ 
    170 root      20   0       0      0      0 I   0.3   0.0   0:00.04 
      1 root      20   0   22536  13940   9648 S   0.0   0.7   0:01.75 
      2 root      20   0       0      0      0 S   0.0   0.0   0:00.00 
      3 root      20   0       0      0      0 S   0.0   0.0   0:00.00 
      4 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 
      5 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 
      6 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 
      7 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 
      8 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 
     10 root      20   0       0      0      0 I   0.0   0.0   0:00.05 
     11 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 
     12 root      20   0       0      0      0 I   0.0   0.0   0:00.07 
     13 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 

     CPU and memory usage in real time

Load average visible

Press q to exit


3️⃣ List active services


     systemctl list-units --type=service --state=running
  UNIT                                           LOAD   ACTIVE SUB     DESCRIPTION                                                   
  acpid.service                                  loaded active running ACPI event daemon
  chrony.service                                 loaded active running chrony, an NTP client/server
  cron.service                                   loaded active running Regular background program processing daemon
  dbus.service                                   loaded active running D-Bus System Message Bus
  getty@tty1.service                             loaded active running Getty on tty1
  irqbalance.service                             loaded active running irqbalance daemon
  ModemManager.service                           loaded active running Modem Manager
  multipathd.service                             loaded active running Device-Mapper Multipath Device Controller
  networkd-dispatcher.service                    loaded active running Dispatcher daemon for systemd-networkd
  nginx.service                                  loaded active running A high performance web server and a reverse proxy server
  polkit.service                                 loaded active running Authorization Manager
  rsyslog.service                                loaded active running System Logging Service
  serial-getty@ttyS0.service                     loaded active running Serial Getty on ttyS0
  snap.amazon-ssm-agent.amazon-ssm-agent.service loaded active running Service for snap application amazon-ssm-agent.amazon-ssm-agent
  snapd.service                                  loaded active running Snap Daemon
  ssh.service                                    loaded active running OpenBSD Secure Shell server
  systemd-journald.service                       loaded active running Journal Service
  systemd-logind.service                         loaded active running User Login Management
  systemd-networkd.service                       loaded active running Network Configuration
  systemd-resolved.service                       loaded active running Network Name Resolution
  systemd-udevd.service                          loaded active running Rule-based Manager for Device Events and Files
  udisks2.service                                loaded active running Disk Manager
  unattended-upgrades.service                    loaded active running Unattended Upgrades Shutdown
  user@1000.service                              loaded active running User Manager for UID 1000

Many background services running
cron / ssh / docker visible (depends on system)


4️⃣ Inspect one service (example: cron)

systemctl status cron
● cron.service - Regular background program processing daemon
     Loaded: loaded (/usr/lib/systemd/system/cron.service; enabled; preset: enabled)
     Active: active (running) since Mon 2026-02-09 18:16:52 UTC; 7min ago
       Docs: man:cron(8)
   Main PID: 534 (cron)
      Tasks: 1 (limit: 2213)
     Memory: 1.1M (peak: 2.6M)
        CPU: 22ms
     CGroup: /system.slice/cron.service
             └─534 /usr/sbin/cron -f -P

Feb 09 18:16:52 ip-172-31-9-80 systemd[1]: Started cron.service - Regular background program processing daemon.
Feb 09 18:16:52 ip-172-31-9-80 (cron)[534]: cron.service: Referenced but unset environment variable evaluates to an empty string: EXTRA_OPTS
Feb 09 18:16:52 ip-172-31-9-80 cron[534]: (CRON) INFO (pidfile fd = 3)

Service is active and running

Shows service start time

Shows PID and logs summary

(If cron not available, use ssh or docker)


5️⃣ View logs for a service
journalctl -u cron --no-pager | tail -n 20

an 29 16:45:01 ip-172-31-9-80 CRON[2922]: pam_unix(cron:session): session opened for user root(uid=0) by root(uid=0)
Jan 29 16:45:01 ip-172-31-9-80 CRON[2923]: (root) CMD (command -v debian-sa1 > /dev/null && debian-sa1 1 1)
Jan 29 16:45:01 ip-172-31-9-80 CRON[2922]: pam_unix(cron:session): session closed for user root
Jan 29 16:55:01 ip-172-31-9-80 CRON[2935]: pam_unix(cron:session): session opened for user root(uid=0) by root(uid=0)
Jan 29 16:55:01 ip-172-31-9-80 CRON[2936]: (root) CMD (command -v debian-sa1 > /dev/null && debian-sa1 1 1)
Jan 29 16:55:01 ip-172-31-9-80 CRON[2935]: pam_unix(cron:session): session closed for user root
Jan 29 16:57:09 ip-172-31-9-80 systemd[1]: Stopping cron.service - Regular background program processing daemon...
Jan 29 16:57:09 ip-172-31-9-80 systemd[1]: cron.service: Deactivated successfully.
Jan 29 16:57:09 ip-172-31-9-80 systemd[1]: Stopped cron.service - Regular background program processing daemon.


Recent log entries for cron

Confirms service is working

Useful for debugging failures


6️⃣ View system logs
journalctl -xe

he job identifier is 1902.
Feb 09 18:22:05 ip-172-31-9-80 systemd[1]: snap-core22-2193.mount: Deactivated successfully.
░░ Subject: Unit succeeded
░░ Defined-By: systemd
░░ Support: http://www.ubuntu.com/support

System-wide logs

Helpful for troubleshooting boot or service issue

🔹 Mini Troubleshooting Scenario
Problem:

Check if cron service is running properly.

Steps I followed:
systemctl status cron
journalctl -u cron
ps aux | grep cron

Conclusion:

Service is active

No error logs found

Cron jobs should work normally

🧠 What I Learned Today

ps and top help identify performance issues

systemctl is critical for managing services

journalctl is essential for debugging production issues

Most real DevOps problems start with logs