---
title: "Setting Up Java Web Calculator with Maven and Tomcat"
datePublished: Sun Mar 23 2025 14:19:20 GMT+0000 (Coordinated Universal Time)
cuid: cm8lq4yp5000d08lb2230gcql
slug: setting-up-java-web-calculator-with-maven-and-tomcat
tags: devcommunity, devops-articles, trainwithshubham

---

## Introduction

### This guide walks you through setting up a Java Web Calculator application using **Maven**, **Git**, and **Apache Tomcat**. Follow these steps to install dependencies, build the project, and deploy it on Tomcat.

## Why This Build Tool is Useful for Companies

Using **Maven** as a build tool provides several advantages for companies, such as:

* **Dependency Management:** Automatically handles project dependencies and ensures compatibility.
    
* **Standardized Build Process:** Simplifies building, testing, and packaging Java applications.
    
* **Automation & Integration:** Easily integrates with CI/CD pipelines for automated deployment.
    
* **Scalability:** Supports large enterprise applications with modular project structures.
    
* **Consistency:** Provides a uniform development environment across teams.
    

---

## Step 1: Update System Packages

Before installing any dependencies, update your package list:

```bash
sudo apt update
```

## Sep 2: Install Java Development Kit (JDK)

Since the project requires **OpenJDK 17**, install it using:

```bash
sudo apt install openjdk-17-jdk -y
```

Verify the installation:

```bash
java --version
```

## Step 3: Install Maven

Maven is required to build the Java Web Calculator project. Install it using:

```bash
sudo apt install maven -y
```

Check if Maven is installed correctly:

```bash
mvn --version
```

## Step 4: Clone the Java Web Calculator Project

Use Git to clone the repository:

```bash
git clone https://github.com/DevOps-Siba/JavaWebCalculator
```

Navigate into the project directory:

```bash
cd JavaWebCalculator/
ls -l
```

## Step 5: Build the Java Web Application

1. Validate the project:
    

```bash
mvn validate
```

2. Compile the Java source code:
    

```bash
mvn compile
```

3. Run unit test:
    

```bash
mvn test
```

4. Package the application into a war file:
    

```bash
mvn package
```

5. Run verify the build:
    

```bash
mvn verify
```

6. Install dependencies into the local Maven repository:
    

```bash
mvn install
```

Check the **target/** directory to confirm that the **.war** file has been generated:

```bash
cd target/
ls
```

## Step 6: Download and Install Apache Tomcat

Download **Apache Tomcat 9**:

```bash
wget https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.102/bin/apache-tomcat-9.0.102.tar.gz
```

Extract the archive:

```bash
tar -xvf apache-tomcat-9.0.102.tar.gz
```

Rename and move the extracted folder to `/opt/`:

```bash
mv apache-tomcat-9.0.102 tomcat9
sudo cp -r tomcat9/ /opt
```

Change ownership of the directory:

```bash
sudo chown -R ubuntu:ubuntu /opt/tomcat9/
```

## Step 7: Deploy Java Web Calculator to Tomcat

1. Copy the generated **.war** file to Tomcat’s `webapps` directory:
    

```bash
cp target/*.war /opt/tomcat9/webapps/
```

2. Start Tomcat:
    

```bash
/opt/tomcat9/bin/startup.sh
```

3. Access the application in your browser:
    

```bash
http://<your-server-ip>:8080/JavaWebCalculator
```

## Conclusion

Following these steps, you have successfully set up and deployed the Java Web Calculator using Maven and Apache Tomcat. If you face any issues, check the Tomcat logs:

```bash
cat /opt/tomcat9/logs/catalina.out
```

Using Maven helps companies streamline their **software development lifecycle**, improve **code maintainability**, and enhance **team collaboration**. This ensures faster development, testing, and deployment of Java applications.