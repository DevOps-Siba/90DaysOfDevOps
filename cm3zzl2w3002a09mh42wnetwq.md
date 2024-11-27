---
title: "DevOps Day#2"
datePublished: Wed Nov 27 2024 14:34:03 GMT+0000 (Coordinated Universal Time)
cuid: cm3zzl2w3002a09mh42wnetwq
slug: devops-day2
tags: 90daysofdevops, trainwithshubham, abhishek-veeramalla

---

## **Listing of basic Linux commands :**

### Listing commands:

* List the sub directories and files avaiable in the present directory
    
    ```bash
    ls option_flag arguments 
    ```
    

Examples:

* List the files and directories in long list format with extra information
    
    ```bash
    ls -l
    ```
    
* List all including hidden files and directory
    
    ```bash
    ls -a
    ```
    
* List all the files having .sh extension.
    
    ```bash
    ls *.sh 
    ```
    
* List the files and directories with index numbers inodes
    
    ```bash
    ls -i
    ```
    
* List only directories.(we can also specify a pattern)
    
    ```bash
    ls -d */
    ```
    

### Directoy commands

* Print work directory. Gives the present working directory.
    
    ```bash
    pwd
    ```
    
* Change directory to the provided path
    
    ```bash
    cd path to directory
    cd devops ("devops" directory name)
    ```
    
* Change directory to the home directory
    
    ```bash
    cd ~ or just cd 
    ```
    
* Go to the last working directory.
    
    ```bash
    cd -
    ```
    

* Change directory to one step back.
    
    ```bash
    cd .. 
    ```
    
* Change directory to 2 levels back.
    
    ```bash
    cd ../.. 
    ```
    
* To make a directory in a specific location
    
    ```bash
    mkdir directoryName 
    ```
    

**Examples**:

```bash
mkdir newFolder              # make a new folder 'newFolder'

mkdir .NewFolder              # make a hidden directory (also . before a file to make it hidden)

mkdir A B C D                  #make multiple directories at the same time

mkdir /home/user/Mydirectory   # make a new folder in a specific location

mkdir -p  A/B/C/D              # make a nested directory
```