---
title: "Day#5:Advanced Linux Shell Scripting for DevOps Engineers with User Management"
datePublished: Thu Dec 19 2024 20:45:52 GMT+0000 (Coordinated Universal Time)
cuid: cm4vsjz1x000y09ji610b1kjo
slug: day5advanced-linux-shell-scripting-for-devops-engineers-with-user-management

---

## Introduction

Welcome to Day 5 of the #90DaysOfDevOps challenge! Today, we dive into advanced Linux shell scripting for DevOps engineers, focusing on tasks like creating directories dynamically, backing up your work, and managing users in Linux. Let’s explore these concepts step by step.

### A Thought Experiment

Imagine opening a repository directory named `2023` and discovering 90 sub-directories inside it. What comes to your mind? Were these directories created manually, with a script, or with a single command? The answer might surprise you!

Using the simple command below, all 90 directories were created within seconds:

```bash
mkdir day{1..90
```

## Task 1: Create Directories Using a Shell Script

### Problem Statement

Write a bash script `createDirectories.sh` that, when executed with three arguments (directory name, start number, and end number), creates a specified number of directories dynamically.

### Examples

* Example 1: When executed as `./`[`createDirectories.sh`](http://createDirectories.sh) `day 1 90`, it creates 90 directories as `day1 day2 day3 ... day90`.
    

**\&gt;** Example 2: When executed as `./`[`createDirectories.sh`](http://createDirectories.sh) `Movie 20 50`, it creates 31 directories as `Movie20 Movie21 Movie22 ... Movie50`.

### Implementation

Here’s the script:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1734639848341/7416bb5d-e231-4087-be59-8f9b765ec0a4.png align="center")

### How to Run

1. Save the script as `createDirectories.sh`.
    
2. Make it executabl:
    
    ```bash
    chmod +x createDirectories.sh
    ```
    

Run the script with your desired arguments.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1734640087792/a3020f75-66c5-44fa-a942-f314f1cf0682.png align="center")

## Task 2: Create a Backup Script

### Importance of Backups

Picture this: you’ve spent hours working on a project, only to lose your progress due to an unexpected system crash. Backups are your safety net, ensuring you never lose important work. As a DevOps engineer, automating this process is crucial.

### Implementation

Here’s a backup script to keep your work safe:

```bash
#!/bin/bash

# Define variables
source_dir="$HOME/work"
destination_dir="$HOME/backup"
timestamp=$(date +"%Y%m%d_%H%M%S")
backup_file="backup_$timestamp.tar.gz"

# Create backup directory if it doesn't exi
mkdir -p "$destination_dir"

# Create a compressed tarball of the source directory
if tar -czf "$destination_dir/$backup_file" -C "$source_dir" .; then
  echo "Backup successful: $destination_dir/$backup_file"
else
  echo "Backup failed."
  exit 1
fi
```

---