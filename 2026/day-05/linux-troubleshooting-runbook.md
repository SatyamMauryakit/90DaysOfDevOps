Day 05 – Linux Troubleshooting Runbook

🎯 Target Service / Process

Service chosen: cron
Reason: Core system scheduler used for automation jobs.
 uname -a
Linux ip-172-31-9-80 6.14.0-1018-aws #18~24.04.1-Ubuntu SMP Mon Nov 24 19:46:27 UTC 2025 x86_64 x86_64 x86_64 GNU/Linux
Linux kernel version and architecture displayed.

2️⃣ OS version
cat /etc/os-release


PRETTY_NAME="Ubuntu 24.04.3 LTS"
NAME="Ubuntu"
VERSION_ID="24.04"
VERSION="24.04.3 LTS (Noble Numbat)"
VERSION_CODENAME=noble
ID=ubuntu
ID_LIKE=debian
HOME_URL="https://www.ubuntu.com/"
SUPPORT_URL="https://help.ubuntu.com/"
BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
UBUNTU_CODENAME=noble
LOGO=ubuntu-logo

Confirmed OS distribution and version.



3️⃣ Create demo directory

mkdir /tmp/runbook-demo

Directory created successfully.

4️⃣ Copy file and verify

cp /etc/hosts /tmp/runbook-demo/hosts-copy
ls -l /tmp/runbook-demo

File copied and visible with correct permissions.

🔹 Snapshot – CPU & Memory
5️⃣ Real-time CPU and memory
top
System idle, low CPU usage, no runaway process.

6️⃣ Memory usage
free -h

   total        used        free      shared  buff/cache   available
Mem:            1910         369        1185           2         519        1541
Swap:              0           0           0

Sufficient free memory available.

🔹 Snapshot – Disk & IO
7️⃣ Disk usage
df -h

Filesystem       Size  Used Avail Use% Mounted on
/dev/root         19G  4.4G   14G  24% /
tmpfs            956M     0  956M   0% /dev/shm
tmpfs            383M  884K  382M   1% /run
tmpfs            5.0M     0  5.0M   0% /run/lock
efivarfs         128K  3.8K  120K   4% /sys/firmware/efi/efivars
/dev/nvme0n1p16  881M  155M  665M  19% /boot
/dev/nvme0n1p15  105M  6.2M   99M   6% /boot/efi
tmpfs            192M   12K  192M   1% /run/user/1000

Root filesystem below 70% usage.

8️⃣ Log directory size
du -sh /var/log

Log size reasonable.


🔹 Snapshot – Network

9️⃣ Listening ports
ss -tulpn

SSH and system services listening

🔟 Connectivity test
ping google.com -c 3

Packets sent and received successfully.

🔹 Logs Reviewed
1️⃣ Service logs
journalctl -u cron -n 50

No recent errors

2️⃣ System logs
tail -n 50 /var/log/syslog
No critical failures.




