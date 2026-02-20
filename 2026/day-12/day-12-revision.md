# Day 12 – Revision (Days 01–11)

## Mindset & Plan Review
This section helps me reflect on why I started this journey and whether my goals still make sense.

- My original goal:
  Become confident with Linux fundamentals and DevOps basics.

- Are my goals still valid?
  Yes. I still want to build strong foundations before moving to advanced DevOps tools.

- Changes I want to make in my plan:
  - Spend more time on Linux commands.
  - Practice daily instead of only reading.
  - Take short notes after each session.

---

## Processes & Services (Hands-on)

Linux processes and services show what is running on the system and whether services are healthy.

Commands I ran:
- ps aux → Shows all running processes.
- systemctl status ssh → Checks if SSH service is running.
- journalctl -u ssh → Shows logs for SSH service.

Observations:
- I learned how to identify running processes.
- I can quickly check if a service is active or failed.
- Logs help in understanding errors.

---

## File Skills Practice

File and directory operations are the backbone of Linux usage.

Commands practiced today:
- mkdir test_dir → Creates a directory.
- echo "hello linux" >> file.txt → Appends text to file.
- chmod 755 file.txt → Gives owner full permission, others read & execute.
- chown user:user file.txt → Changes ownership.
- ls -l → Displays permissions and ownership.

What I noticed:
- Permissions control who can read, write, or execute.
- Wrong permissions can break applications.

---

## Cheat Sheet – Top 5 Commands I’ll Use First

1. ls → List files and folders.
2. cd → Move between directories.
3. pwd → Know current directory.
4. systemctl status → Check service health.
5. ps aux → View running processes.

Why these are important:
- They help in quick navigation and troubleshooting.

---

## User / Group Sanity Check

Users and groups control access in Linux.

Scenario:
- Created user: testuser  
  useradd testuser
- Verified with:  
  id testuser
- Changed ownership of file:  
  chown testuser:testuser sample.txt

Result:
- testuser became owner of the file.

---

## Mini Self-Check

1) Which 3 commands save you the most time right now, and why?  
- ls → Quickly see files.  
- systemctl status → Check service state.  
- chmod → Fix permission issues.

2) How do you check if a service is healthy?  
- systemctl status <service>  
- journalctl -u <service>  
- ps aux | grep <service>

3) How do you safely change ownership and permissions?  
Example:
chown user:user file.txt  
chmod 755 file.txt  

4) What will you focus on improving in the next 3 days?  
- More Linux practice.  
- Understand permissions better.  
- Learn basic networking commands.

---

## Key Takeaways

- Linux fundamentals are very important.
- Practice is more effective than only reading.
- Small daily progress builds strong skills.