---
title: "Ansible: Simplifying Automation for Everyone"
datePublished: Wed Dec 18 2024 19:32:23 GMT+0000 (Coordinated Universal Time)
cuid: cm4uahmuv000m09l4ha0jbctj
slug: ansible-simplifying-automation-for-everyone
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1734550330163/52164ac8-3e06-480d-ad55-a5d6a51166c3.jpeg
tags: twitter, devcommunity, trainwithshubham, tws, abhishek-veeramalla

---

### **Introduction:**

Ansible is a simple, powerful tool that helps automate tasks like managing servers, installing software, and configuring systems. Whether you're from a technical background or not, this guide will help you understand Ansible step-by-step, with visual examples and hands-on projects.

## **What is Ansible?**

Ansible is an **open-source tool for automation**. It helps manage servers, applications, and networks by automating tasks like installing software, setting up configurations, and managing services.

### **How Does Ansible Work?**

1. **No agents**: You don’t need to install any software on the servers you manage. Ansible uses SSH (a way to securely communicate between computers).
    
2. **Playbooks**: Tasks are written in a simple, human-readable format called YAML. Think of it like writing down instructions in a step-by-step list.
    
3. **Control Node**: You run Ansible from one computer (the control node) to manage many other computers (the managed nodes).
    

---

## **Why Use Ansible?**

1. **Simplicity**: No programming required. Just write what you want Ansible to do in plain language (YAML format).
    
2. **Saves Time**: Automates repetitive tasks like installing software on multiple computers.
    
3. **Reliability**: Ensures the same task is done consistently every time.
    

**Flexibility**: Works with many operating systems and software.

### **How to Use Ansible: A Step-by-Step Guide**

### **Step 1: Install Ansible**

1. Open your terminal.
    
2. Run these commands to install Ansible:
    
    ```bash
    sudo apt-add-repository ppa:ansible/ansible
    sudo apt update
    sudo apt install ansible -y
    ```
    
3. Verify the installation:
    
    ```bash
    ansible --version
    ```
    

### **Step 2: Create an Inventory File**

The inventory file tells Ansible which servers to manage.

Open the file:

```bash
sudo vim /etc/ansible/hosts
 
```

Add your server details:

```bash
ini
[web_servers]
server1 ansible_host=192.168.1.10 
server2 ansible_host=192.168.1.12
server1 ansible_user=ubuntu 
server2 ansible_user=ec2-user
ansible_ssh_private_key_file=/path/to/private/key
```

Adjust private key permissions:

```bash
chmod 400 /home/ubuntu/keys/ansible-server.pwm
```

#### **Step 3: Run Your First Command**

Test the connection with a "ping":

```bash
ansible web_servers -m ping
```

**If successful, you’ll see** `pong` **responses from the servers.**

### **Step 3: Run Simple Commands**

Now that connectivity is confirmed, let’s use Ansible to run some basic tasks.

#### **Example 1: Check Disk Usage**

```bash
ansible servers -a "df -h"
```

#### **Example 2: Update System Packages**

```bash
ansible servers -b -a "sudo apt update"
```

#### **Example 3: Install Software (e.g., NGINX Web Server)**

```bash
ansible servers -b -a "sudo apt install nginx -y"
```

#### **Example 4:** Use Ansible to monitor CPU usage:

create a file called show\_update.yml file then write below -

```yaml

- name: Monitor CPU Usage
  hosts: servers
  tasks:
    - name: Show CPU Load
      command: uptime
```

Run the playbook:

```bash
ansible-playbook show_update.yml
```

#### **Example 4: File Management Example**: Automate creating a directory:

```yaml
- name: Create Directory
  hosts: servers
  tasks:
    - name: Create a logs folder
      file:
        path: /var/logs/custom_logs
        state: directory
        mode: '0755'
```

#### **Example 5:** Automate Tasks with Playbooks

A **Playbook** is a file where you define a list of tasks. For example:

**Example Playbook: Installing NGINX**  
Create a file called `install_nginx.yml`:

```yaml
- name: Install NGINX on web servers
  hosts: web_servers
  become: yes
  tasks:
    - name: Update package list
      apt:
        update_cache: yes

    - name: Install NGINX
      apt:
        name: nginx
        state: present
```

Run the playbook:

```bash
ansible-playbook install_nginx.yml
```

### **Hands-On Project: Set Up a Static Web Page with Ansible**

#### **Objective**

Automate the deployment of a static web page on multiple servers.

#### **Step 1: Prerequisites**

* Ansible installed on the control node.
    
* At least one managed server.
    

#### **Step 2: Write the Playbook**

Create a file called `deploy_webpage.yml`:

```yaml
 
- name: Deploy a static webpage
  hosts: web_servers
  become: yes
  tasks:
    - name: Install NGINX
      apt:
        name: nginx
        state: present

    - name: Copy the HTML file
      copy:
        src: /path/to/index.html
        dest: /var/www/html/index.html

    - name: Restart NGINX
      systemd:
        name: nginx
        state: restarted
```

---

#### **Step 3: Run the Playbook**

Run the following command:

```bash
ansible-playbook deploy_webpage.yml
```

---

#### **Step 4: Verify the Deployment**

Visit your server's IP in a browser (`http://<your_server_ip>`) to view the web page.

---

---