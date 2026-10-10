# Day 2 — Linux Fundamentals and Process Management

## 🎯 Learning Objectives

Understand the Linux filesystem, users, groups, permissions, and process management — essential concepts for working with Linux servers in DevOps.

## 1. Linux Fundamentals

Linux is an operating system widely used for servers, cloud infrastructure, containers, and DevOps tools.

### Basic Linux Architecture

```text
User
  ↓
Shell
  ↓
Kernel
  ↓
Hardware
```

- **Shell:** Accepts commands and communicates with the operating system.
- **Kernel:** Manages CPU, memory, processes, devices, and system resources.
- **Hardware:** Physical or virtual computing resources.

## 2. Linux Filesystem

Linux uses a hierarchical filesystem that starts at the root directory `/`.

| Directory  | Purpose                              |
| ---------- | ------------------------------------ |
| `/`        | Root of the filesystem               |
| `/home`    | Home directories of regular users    |
| `/root`    | Home directory of the root user      |
| `/etc`     | System and application configuration |
| `/var`     | Frequently changing data             |
| `/var/log` | System and application logs          |
| `/tmp`     | Temporary files                      |
| `/usr`     | Many system programs and libraries   |
| `/opt`     | Optional or additional software      |

### Absolute and Relative Paths

- **Absolute path:** Starts from `/`, for example `/home/debdulal/devops-learning`.
- **Relative path:** Starts from the current working directory, for example `day-02/README.md`.

The current working directory is the directory in which your shell is currently operating.

## 3. Users and Groups

Linux supports multiple users and groups to control access to files and system resources.

- **Regular user:** Performs normal tasks with limited permissions.
- **Root user:** Has extensive administrative privileges.
- **Group:** Allows multiple users to share access permissions.

### Commands Practiced

| Command    | Purpose                                          |
| ---------- | ------------------------------------------------ |
| `whoami`   | Display the current username                     |
| `id`       | Display user ID and group information            |
| `groups`   | Display groups associated with the current user  |
| `useradd`  | Create a user                                    |
| `passwd`   | Set or change a user's password                  |
| `userdel`  | Delete a user                                    |
| `groupadd` | Create a group                                   |
| `groupdel` | Delete a group                                   |
| `usermod`  | Modify a user account                            |
| `pwd`      | Display the current directory                    |
| `ls -la`   | List files, including hidden files, with details |

Administrative commands may require `sudo` or root privileges.

## 4. File Ownership

Every file or directory has an owner and an associated group.

### Commands

```bash
chown debdulal file.txt
chgrp developers file.txt
```

- `chown` changes file ownership.
- `chgrp` changes the file's group.

To change both owner and group:

```bash
sudo chown debdulal:developers file.txt
```

Changing a file's group does not automatically make the owner a member of that group.

## 5. Linux Permissions

Linux permissions control who can read, modify, or execute a file.

| Permission | Symbol | Numeric value |
| ---------- | ------ | ------------: |
| Read       | `r`    |             4 |
| Write      | `w`    |             2 |
| Execute    | `x`    |             1 |

Permissions apply to three categories:

- **Owner:** The file's owner.
- **Group:** Users belonging to the file's group.
- **Others:** Everyone else.

### Numeric Permission Examples

| Mode  | Symbolic form | Meaning                                                          |
| ----- | ------------- | ---------------------------------------------------------------- |
| `755` | `rwxr-xr-x`   | Owner has all permissions; group and others can read and execute |
| `644` | `rw-r--r--`   | Owner can read and write; group and others can read              |
| `700` | `rwx------`   | Only the owner has permissions                                   |

### Commands

```bash
chmod 755 script.sh
chmod 644 file.txt
chmod 700 private-file
```

`chmod` changes permissions.

Understanding permissions helps troubleshoot errors such as permission denied when accessing files, configuration, or deployment scripts.

## 6. Process Management

A **program** is software stored on disk. A **process** is a running instance of a program.

### Important Terms

- **PID:** Process ID — identifies a running process.
- **PPID:** Parent Process ID — identifies the parent process.
- **Parent process:** A process that creates or starts another process.
- **Child process:** A process created by another process.

On modern Ubuntu systems, PID 1 is typically `systemd`, which initializes and manages system services.

### Process States

- **Running:** Executing or ready to execute.
- **Sleeping:** Waiting for an event or resource.
- **Stopped:** Suspended.
- **Zombie:** Finished execution but its process-table entry has not yet been fully collected by its parent.

### Process Resources

Processes can consume:

- CPU
- RAM
- Disk I/O
- Network resources

Monitoring these resources helps identify performance issues on servers.

## 7. Process vs. Service

A **process** is a running instance of a program.

A **service** is a program or background workload managed to provide a continuing function, often with operating-system service management.

For example, a web server can run as a process and be managed as a service. Services may be configured to start automatically when the system boots.

## 8. Process-Related Commands

| Command    | Purpose                                            |
| ---------- | -------------------------------------------------- |
| `ps`       | Display a snapshot of processes                    |
| `ps aux`   | Display detailed information about processes       |
| `top`      | Monitor processes and resource usage interactively |
| `htop`     | Interactive process monitor, if installed          |
| `kill PID` | Send the default termination signal to a process   |
| `jobs`     | List jobs managed by the current shell             |
| `fg`       | Bring a shell job to the foreground                |
| `bg`       | Resume a suspended shell job in the background     |

**Important:** `ps aux` provides a snapshot. `top` provides continuously refreshed monitoring. The `kill` command sends a signal; it does not always terminate a process immediately.

## 9. DevOps Relevance

These concepts are useful when troubleshooting Linux servers and cloud environments.

For example, if an application is not working:

1. Check whether its process is running.
2. Inspect its configuration files.
3. Check logs under relevant directories such as `/var/log`.
4. Verify file ownership and permissions.
5. Investigate CPU and memory usage.

This provides a systematic approach to diagnosing common server problems.

## 10. Key Takeaways

- Linux organizes files and directories under `/`.
- Users and groups help control access.
- Ownership and permissions determine who can access files.
- Processes represent running programs and consume system resources.
- Services provide managed background functionality.
- Process-monitoring commands help investigate server issues.
- These fundamentals support later work with AWS, deployment, containers, and automation.

## Progress

- [x] Linux filesystem and directory structure — theory
- [x] Users, groups, and ownership — reviewed
- [x] File permissions — reviewed
- [x] Process and service concepts — theory
- [x] Process commands — reviewed
- [x] Hands-on process-management lab — to be completed
