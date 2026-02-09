🗂️ File System Commands

ls            # List files and directories
ls -la        # List all files with permissions (including hidden)
pwd           # Show current directory path
cd /path      # Change directory
mkdir test    # Create a directory
rmdir test    # Delete empty directory
rm file.txt   # Delete file
rm -rf dir    # Delete directory forcefully
cp a b        # Copy file
mv a b        # Move or rename file
touch file    # Create empty file
stat file     # Show file details
du -sh dir    # Show directory size
df -h         # Show disk usage



⚙️ Process Management Commands

ps aux            # List all running processes
top               # Real-time process monitoring
htop              # Enhanced process viewer (if installed)
pidof nginx       # Get PID of a process
kill PID          # Kill process by PID
kill -9 PID       # Force kill process
pkill nginx       # Kill process by name
nice -n 10 cmd    # Set process priority
uptime            # System running time and load
free -h           # Memory usage
vmstat            # CPU and memory statistics


🌐 Networking & Troubleshooting Commands


ip addr           # Show IP addresses
ip route          # Show routing table
ping google.com   # Test network connectivity
curl ifconfig.me  # Get public IP
netstat -tulnp    # Show listening ports
ss -tulnp         # Modern alternative to netstat
dig google.com    # DNS lookup
traceroute google.com  # Trace network path


📜 Log & Debugging Commands 

cat file.log          # View file content
less file.log         # Scroll through logs
tail file.log         # Show last lines
tail -f app.log       # Live log monitoring
grep error app.log    # Search text in file
journalctl -xe        # Systemd logs



🔐 Permission & User Commands

chmod 755 file        # Change file permissions
chown user:file       # Change ownership
whoami                # Current user
id                    # User and group info
sudo command          # Run command as root



chmod 755 file        # Change file permissions
chown user:file       # Change ownership
whoami                # Current user
id                    # User and group info
sudo command          # Run command as root
