---
title: "Day#5:Advanced Linux Shell Scripting for DevOps Engineers with User Management"
datePublished: Thu Dec 19 2024 20:45:52 GMT+0000 (Coordinated Universal Time)
cuid: cm4vsjz1x000y09ji610b1kjo
slug: day5advanced-linux-shell-scripting-for-devops-engineers-with-user-management
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1734723234110/0568e31a-50b7-41f2-b26c-03149c4f1e3a.png
tags: twitter, devops, devcommunity, tws, abhishek-veeramalla

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

#### 1\. **Check If the** `Documents` Folder Exists for Source Directory

* Run the following command:
    
    ```bash
    ls /home/ubuntu/Documents
    ```
    
* If the folder does not exist, create it:
    
    ```bash
    mkdir -p /home/ubuntu/Documents
    ```
    

#### 2\. **Check If the “Documents” Folder Contains Files**:

* If the folder exists but is empty, add a test file:
    
    ```bash
    echo "This is a test file." > /home/ubuntu/Documents/test_file.txt
    ```
    

#### 4\. **Updated Script**s

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1734708358305/6a70edb4-0ead-473f-9f74-f938e5fc19cb.png align="center")

### Steps to Run:

1. **Save the Script**: Ensure the script is saved with the changes.
    
2. **Make Sure the** `Documents` Folder Exists:
    
    * Verify:
        
        ```bash
        ls ~/Documents
        ```
        
    * If it's empty, add test files:
        
        ```bash
        echo "Test file 1" > ~/Documents/file1.txt
        echo "Test file 2" > ~/Documents/file2.txt
        ```
        
3. **Run the Script**:
    
    ```bash
    ./backup.sh
    ```
    

### Expected Output:

If everything is set up correctly, the output should look something like this:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1734708656097/c052ef89-5960-487d-9b64-1ea793010307.png align="center")

## Task 3: Read About Cron and Crontab to Automate the Backup Script:

**Cron** is a time-based job scheduler in Unix-like operating systems, including Linux. It automates the execution of scripts or commands at specified intervals or times.

**Crontab** (short for "cron table") is a configuration file that specifies what tasks to run and when to run them. Each user on a system can have their own crontab file.

### **How Cron and Crontab Work**

1. **Cron Daemon (**`crond`):
    
    * A background service that reads crontab files and executes the specified tasks on schedule.
        
2. **Crontab Command**:
    
    * `crontab` allows users to manage their scheduling entries.
        
3. **Crontab Syntax**: A crontab entry consists of **time fields** and the **command to execute**:
    
    ```bash
    MIN HOUR DOM MON DOW COMMAND
    ```
    
    * `MIN`: Minute (0-59)
        
    * `HOUR`: Hour (0-23)
        
    * `DOM`: Day of the Month (1-31)
        
    * `MON`: Month (1-12 or names like `jan`)
        
    * `DOW`: Day of the Week (0-7, where both 0 and 7 represent Sunday)
        
    * `COMMAND`: The script or command to run
        

### **Common Commands for Crontab**

1. **List Crontab Entries**:
    
    ```bash
     crontab -l
    ```
    
2. **Edit Crontab**:
    
    ```bash
     crontab -e
    ```
    
    * This opens the crontab file in your default text editor (usually `nano`).
        
3. **Remove Crontab**:
    
    ```bash
     crontab -r
    ```
    

### **Automating the Backup Script**

You can use cron to automate the execution of your backup script.

#### **Steps to Automate the Backup Script**

1. **Ensure the Script is Ready**:
    
    * Save your script, for example, as `/home/ubuntu/`[`backup.sh`](http://backup.sh).
        
    * Make it executable:
        
        ```bash
         chmod +x /home/ubuntu/backup.sh
        ```
        
2. **Open the Crontab File**:
    
    ```bash
     crontab -e
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1734716426643/214aadf9-397e-4edc-8dcc-fcfb6df21e0b.png align="center")
    
3. **Add a New Cron Job**: Add an entry to schedule the backup script. For example:
    

To run the script every day at 2:00 AM:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1734716906090/51752c23-27e4-49c8-b66f-61a838df2e22.png align="center")

Explanation of the fields:

* `0`: Minute (at the start of the hour)
    
* `2`: Hour (2 AM)
    
* `*`: Every day of the month
    
* `*`: Every month
    
* `*`: Every day of the week
    

1. **Save and Exit**:
    
    * Save the file and exit the editor. The cron daemon will automatically pick up the changes.
        
2. **Verify the Cron Job**:
    

List your crontab entries to ensure the job is scheduled:

```bash
crontab -l
```

**Delete crontab :**

```bash
crontab -i -r
```

## Task 4: **Read About User Management:**

* A user is an entity in a Linux operating system that can manipulate files and perform several other operations. Each user is assigned an ID that is unique within the system. IDs 0 to 999 are assigned to system users, and local user IDs start from 1000 onwards.
    
* Create 2 users and display their usernames.
    

**Script for User Management:**

```bash
#!/bin/bash

# Function to create a new user
create_user() {
    local username=$1
    if id "$username" &>/dev/null; then
        echo "User $username already exists."
    else
        sudo useradd "$username"
        echo "User $username created successfully."
    fi
}

# Function to set a password for the user
set_password() {
    local username=$1
    echo "Setting password for $username..."
    sudo passwd "$username"
}

# Function to display user details
display_user_details() {
    local username=$1
    echo "Details for user $username:"
    id "$username"
    echo
}

# Main script execution
echo "Starting user management script..."

# Create two users
USER1="TWS"
USER2="Junoon"

create_user "$USER1"
create_user "$USER2"

# Set passwords for the users
set_password "$USER1"
set_password "$USER2"

# Display the usernames and details
echo "Displaying usernames and details:"
display_user_details "$USER1"
display_user_details "$USER2"

echo "User management script completed."
```

#### **Step 1: Create Two Users**

To create a user, we will use the `useradd` command. We can also specify additional parameters such as the user’s home directory and shell.

Here are the commands to create two users, TWS and Junoon:

```bash
sudo useradd TWS
sudo useradd Junoon
```

This will create two users: **TWS** and **Junoon**. By default, these users will be assigned UIDs starting from 1000 (or the next available UID in your system).

#### **Step 2: Set Password for the Users**

Once the users are created, we need to assign passwords for them. This can be done using the `passwd` command.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1734719615163/095328b5-2719-402f-8e17-e74b97709e65.png align="center")

You'll be prompted to enter a password for each user.

#### **Step 3: Display Usernames and UIDs**

To display the usernames and UIDs, you can use the `id` command, which will show the UID, GID (Group ID), and groups the user belongs to.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1734719716573/69a2e4b6-63bb-4f77-ba00-dcf7661249e3.png align="center")

Alternatively, you can display the usernames directly by running:

```bash
whoami
```

This command will return the current logged-in user. To check other users, you can inspect the `/etc/passwd` file, which contains user information.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1734719901768/952dc1a4-ec55-4b6f-ae45-deb0e53be978.png align="center")

This will return lines like:

```bash
TWS:x:1001:1001::/home/TWS:/bin/sh
Junoon:x:1002:1002::/home/Junoon:/bin/sh
```

Here, 1001 and 1002 are the UIDs of TWS and Junoon, respectively.

#### **Step 4: Displaying Usernames**

To display only the usernames without any additional details, you can use:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1734720466277/c975af84-2eb7-424f-a5fd-0d4835b8b994.png align="center")

This will display a list of all usernames in the system, including TWS and Junoon.

---

### **Summary: Key Concepts in User Management**

* **User IDs (UIDs)**: Every user has a unique identifier in Linux. System users have UIDs ranging from 0 to 999, and local users start from UID 1000.
    
* **Creating Users**: The `useradd` command is used to create new users, while the `passwd` command assigns a password to the user.
    
* **Displaying User Info**: The `id` and `whoami` commands are useful for viewing user information, while `/etc/passwd` contains a list of users and their associated details.
    

---

---