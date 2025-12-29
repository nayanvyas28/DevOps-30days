# Day 05 – Shell Scripting & Automation for DevOps

## What is Shell Scripting?
Shell scripting is writing commands in a file to automate tasks.

Benefits:
- Saves time
- Reduces human error
- Automates repetitive work

Shell used: Bash (Bourne Again Shell)

---

## Creating a Shell Script
1. Create file
2. Add shebang
3. Give execute permission

Example:
#!/bin/bash

---

## Variables
Variables store values.

Example:
NAME="DevOps"
echo "Welcome $NAME"

---

## Taking User Input
read is used to take input.

Example:
read USER
echo "Hello $USER"

---

## If–Else Condition
Used for decision making.

Example:
if [ $AGE -gt 18 ]
then
  echo "Adult"
else
  echo "Minor"
fi

---

## Loops
Used for repetition.

### For Loop
for i in 1 2 3
do
  echo $i
done

---

## Real Automation Use Cases
- Disk usage monitoring
- Service health check
- Backup scripts
- Log cleanup

---

## Cron Jobs
Cron is used to schedule scripts.

View cron:
crontab -l

Edit cron:
crontab -e

Example (run script daily at 2 AM):
0 2 * * * /home/ubuntu/backup.sh

---

## What I Learned Today
- Bash scripting basics
- Variables & conditions
- Loops
- Automating Linux tasks
- Scheduling jobs with cron

---

## Interview Notes
- Shell scripts automate tasks
- Cron schedules scripts
- Used heavily in DevOps pipelines
