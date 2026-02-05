# linux Architecture , Processes, and systemd

## 1. Core Componets of Linux 

### Kernel 
- Heart of the operating system
- Manages CPU, memory , disk ,and hardware devices
- Provides system calls so programs can talk to hardware

Examples:
- Process scheduling
- Memory management
- Device drivers

### User Space 
- Where user programs run
- Includes shells, applications, and utillities
Examples:
- bash, ls ,ps , top, vim , docker

### Init/ systemd 
- First process started bt the  curnel (PID =1)
- Starts and manages all other services
- Controls boot process and service lifecycle


  ## 3. Process States

- **Running (R)** → Currently executing  
- **Sleeping (S)** → Waiting for resource (disk, network, input)  
- **Uninterruptible Sleep (D)** → Waiting for I/O  
- **Stopped (T)** → Paused by signal  
- **Zombie (Z)** → Finished but parent didn’t clean it  

Zombie = process is dead, entry still exists in process table.


## 4. What systemd Does

systemd is the service manager that:

- Starts services at boot  
- Restarts crashed services  
- Manages dependencies  
- Handles logs  

Key Concepts:
- Unit → service file  
- Target → group of services (like runlevel)


## 5. Common systemd Commands

Check service status:
- systemctl start nginx  -->  Start Service
- systemctl stop nginx --> Stop service
- systemctl enable nginx  --> Enable at boot
- journalctl -u nginx  --> View logs
- ps aux # view running processes
top # live system usage
free -h # memory usage
df -h # disk usage 


  ## 7. Why This Matters for DevOps

- Identify crashed services  
- Debug high CPU / memory  
- Restart failed applications  
- Read logs quickly  

If you understand processes + systemd, you can fix most server issues.

  
