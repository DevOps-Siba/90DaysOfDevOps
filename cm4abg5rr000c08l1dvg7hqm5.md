---
title: "DevOps Day#4:-Basic Linux Shell Scripting for DevOps Engineers"
datePublished: Wed Dec 04 2024 20:03:50 GMT+0000 (Coordinated Universal Time)
cuid: cm4abg5rr000c08l1dvg7hqm5
slug: devops-day4-basic-linux-shell-scripting-for-devops-engineers
tags: devcommunity, trainwithshubham, tws, abhishek-veeramalla

---

If you've ever felt overwhelmed doing the same tasks over and over again on your computer, Linux shell scripting might be your new best friend. It's a superpower for automating tasks, especially in the world of DevOps! Let’s dive into the basics of Linux shell scripting, understand its role in DevOps, and create some beginner-friendly scripts.

### **What is a Kernel?**

The **kernel** is the heart of an operating system. Think of it as the bridge between your computer's hardware and the software you run. It handles tasks like:

* Managing memory.
    
* Running programs.
    
* Communicating with hardware (like your CPU and disk).
    

Without the kernel, your computer wouldn’t know how to execute even the simplest command.

### **What is a Shell?**

A **shell** is like a translator between you (the user) and the kernel. It lets you give instructions (commands) to your computer in a way it understands. There are different types of shells, like:

* **Bash (Bourne Again Shell)** – The most popular shell in Linux.
    
* **Sh (Bourne Shell)** – A simpler, older version of Bash.
    

When you type commands like `ls` or `pwd`, the shell processes them and sends them to the kernel to execute.

### **What is Shell Scripting?**

Shell scripting is writing a series of shell commands in a file, called a script, to automate tasks. Instead of typing commands one by one, you write them once, and the computer runs them for you.

### **Benefits of Shell Scripting**

1. **Automation**: Saves time by handling repetitive tasks.
    
2. **Efficiency**: Performs complex tasks quickly and consistently.
    
3. **Flexibility**: Combines commands to create powerful workflows.
    
4. **Crucial for DevOps**: Automates deployments, manages servers, and handles CI/CD pipelines.
    

---

### **Shell Scripting in DevOps**

In DevOps, shell scripting is indispensable. It helps:

* Automate server provisioning and deployments.
    
* Set up and manage CI/CD pipelines.
    
* Monitor logs and system performance.
    

**Example**: Imagine you need to deploy an application to 10 servers. Instead of doing it manually, a shell script can deploy it to all servers with a single command.

**Task 1: Explain in your own words and with examples what Shell Scripting means for DevOps.**

Shell Scripting is writing a series of commands in a script file to automate tasks in the Unix/Linux shell. For DevOps, shell scripting is crucial for automating repetitive tasks, managing system configurations, deploying applications, and integrating various tools and processes in a CI/CD pipeline. It enhances efficiency, reduces errors, and saves time.

**Example: Automating server setup for installing apache2 software**

* Create a file “automation.sh” in your Linux machine.
    
* Open your file and write script given below image.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1733344059649/2609343e-65a0-4ce1-900c-e22277b688c3.png align="center")
    
* Give permission for make it executable.
    
* ```bash
    chmod +x automation.sh
    ```
    
* Run this file ./file name .
    
    ```bash
    ./automation.sh
    ```
    
* Then final output you will get Apache server installation done. Check bellow image:
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1733335679222/53068815-fed5-45ec-8cef-d3e5b8c3699c.png align="center")

Task 2: What is `#!/bin/bash`? Can we write `#!/bin/sh` as well?

* `#!/bin/bash` is called a "shebang" line. It indicates that the script should be run using the Bash shell.
    
    * `#!/bin/bash`: Uses Bash as the interpreter. It supports advanced features like arrays, associative arrays, and functions.
        
    * `#!/bin/sh`: Uses the Bourne shell. It’s more POSIX-compliant and is generally compatible with different Unix shells.
        

**Task 3: Write a Shell Script that prints** `I will complete #90DaysOfDevOps challenge`**.**

**Steps**:

1. Save the script as [`devops.sh`](http://motivation.sh).
    
    ```bash
    #!/bin/bash
    echo "I will complete #90DaysOfDevOps challenge."
    ```
    
2. Make it executable: chmod +x devops.sh
    
3. Run the script : ./devops.sh
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1733337988209/191b28a0-268a-4d86-926f-b2211a4620b4.png align="center")
    
    ## `Output`:
    

```bash
I will complete #90DaysOfDevOps challenge.
```

**Task 4: Write a Shell Script that takes user input, input from arguments, and prints the variables.**

**Steps**:

1. Save the script as [`input.sh`](http://motivation.sh).
    
2. Make it executable: chmod +x devops.sh
    
3. Run the script with argument:
    
    ```bash
    ./input.sh siba  Anand
    ```
    
    4 . Final output:
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1733341094570/3984a839-7820-4693-8b93-eb53c204d6ff.png align="center")

**Task 5: Provide an example of an If-Else statement in Shell Scripting by comparing two numbers.**

Let’s compare two numbers using an `if-else` statement.

**Script**:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1733343217959/828b76d3-bb46-4376-8850-c0864a9c7a8a.png align="center")

**Steps**:

1. Save the above script as [`ifelse.sh`](http://compare.sh).
    
2. Make it executable:
    
    ```bash
    chmod +x ifelse.sh
    ```
    
3. Run the script:
    
    ```bash
    ./ifelse.sh
    ```
    

4\. Output:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1733342171317/a58c37a8-81e9-42e5-a8c9-8b9955f23e0d.png align="center")

Step-by-Step Explanation of the If-Else Script

1. **Define Variables**: `num1` and `num2` are assigned values.
    
2. **If Condition**: `[ $num1 -gt $num2 ]` checks if `num1` is greater than `num2`.
    
3. **Else Statement**: Executes when the condition is false.
    

## **“With practice, you'll unlock its full potential and confidently tackle even complex tasks**.”

---