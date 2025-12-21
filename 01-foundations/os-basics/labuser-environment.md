# labuser Environment Setup (Arch Linux)
**Path:** 01-foundations/os-basics/labuser-environment.md

---

## Purpose

This document records the creation and use of a **non-root lab user** (`labuser`) on Arch Linux to practice operating system fundamentals safely under real privilege restrictions.

This setup allows OS learning without running multiple virtual machines, which is necessary due to limited RAM.

---

## System Context

- OS: Arch Linux
- Desktop: KDE Plasma (Wayland)
- Hardware constraint: Low RAM
- Strategy: Learn OS internals directly on the host system using isolation via users instead of VMs

---

## Step 1: Create a Dedicated Lab User

Create a new user with a home directory and bash shell:

```bash
sudo useradd -m -s /bin/bash labuser
```

Set a password for the user:

```bash
sudo passwd labuser
```

Verify the user exists:

```bash
id labuser
```

Expected:
- Unique UID
- Primary group assigned
- No sudo privileges

---

## Step 2: Switch to the Lab User

Switch from the main user to the lab user:

```bash
su - labuser
```

If authentication fails:
- Ensure the password entered is for `labuser`
- Ensure the user was created correctly

Confirm current user:

```bash
whoami
```

Expected output:

```text
labuser
```

---

## Step 3: Verify Privilege Restrictions

Test sudo access:

```bash
sudo ls
```

Expected output:

```text
Sorry, user labuser may not run sudo on <hostname>.
```

This confirms:
- `labuser` has no administrative privileges
- OS permission boundaries are enforced

---

## Step 4: Confirm Home Directory Isolation

Check current directory:

```bash
pwd
```

Expected:

```text
/home/labuser
```

List contents:

```bash
ls -la
```

Observation:
- Files are owned by `labuser`
- No access to system directories without permission

---

## Step 5: Process Inspection as Non-Root

View running processes:

```bash
ps aux | head
```

Observe:
- Processes owned by root vs user
- Permission boundaries
- Process IDs (PIDs)

Use interactive monitors (no sudo required):

```bash
top
```

or

```bash
atop
```

---

## Step 6: Memory and Resource Awareness

Check memory usage:

```bash
free -h
```

Inspect kernel memory statistics:

```bash
cat /proc/meminfo | head
```

Purpose:
- Learn real memory pressure behavior
- Understand system limits under constrained hardware

---

## Step 7: Safe Practice Workspace

Create a lab workspace inside the user home directory:

```bash
mkdir -p ~/labs
cd ~/labs
```

Recommended activities under `labuser`:
- Bash scripting
- Python scripting
- File permission experiments
- Environment variables
- PATH manipulation
- Process spawning and inspection
- Reading `/proc` and `/sys` (read-only)

---

## Step 8: Exit the Lab User

Return to the main user:

```bash
exit
```

Confirm user switch:

```bash
whoami
```

---

## Documentation Placement Rule

This file belongs ONLY in:

```text
01-foundations/os-basics/labuser-environment.md
```

Reason:
- This is foundational OS learning
- No exploitation or attack activity
- Serves as a permanent reference

Any future exploit, abuse, or attack using this setup must be documented separately in:

```text
04-labs/
```

---

## Summary

- Learning OS fundamentals does NOT require multiple VMs
- User isolation provides realistic constraints
- Low RAM environments mirror real-world servers and targets
- This setup is suitable for early-stage cybersecurity, red teaming, and OS mastery
