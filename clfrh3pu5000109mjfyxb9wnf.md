---
title: "Advanced Linux Commands For Administrator Management"
datePublished: Mon Mar 27 2023 23:41:34 GMT+0000 (Coordinated Universal Time)
cuid: clfrh3pu5000109mjfyxb9wnf
slug: advanced-linux-commands
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1679928114822/ef97c3ec-6ce0-4fa6-871c-796d56ae3e8c.jpeg
tags: linux, devops, 2articles1week, learning-journey, wemakedevs

---

The last time I have we have learned about DevOps terminology and some of the most used basic commands in Linux. If you have not checked it out do take a look at the blog [***here***](https://blog.younussaberi.me/linux-for-devops). because this blog is going to be covering Linux in an advanced section

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1679928357795/2860af78-5584-48ee-88ea-850f6a099b6e.gif align="center")

# Connecting to Linux shell to different end system

One of the best features of Linux is that the shell can be connected remotely to different end systems. To enable it we use SSH (Secured Shell Hosting).

I am going to connect my EC2 instance from the cloud to my local system running on WSL. Before Connecting the machine, I need to have the Pair Key which I have created and download using creating my instance. You can follow up the steps for SSH below

1. Create a key pair
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1679661265851/8f9a157c-d043-4554-b54d-6027b0289752.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1679661269002/2af73955-36f6-462e-a073-9a7c2c385f3b.png align="center")

1. Download it to your local system
    
2. Locate to PEM file and Run the below command
    
    ```bash
    chmod 400 my-linux-server.pem #provides only read access to user
    ssh -i "my-linux-server.pem" ubuntu@ec2-107-23-107-217.compute-1.amazonaws.com
    ```
    
3. Successfully connected 🙌
    
    Now we have connected to our EC2 instance shell from our local system
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1679661998740/9685a971-ca5e-48a7-a832-980dc0302eb7.png align="center")
    
    After being connected, we can start to do tweaks and change to the machine as per our wish and requirement 🐧.
    

# Creating a user & Adding them to a group

The key feature of Linux is multiuser and to get most of the benefit from these, we are going to use the user group and useradd commands. When working in a team each team has its own requirement and use case and to meet their requirement the group is been used. Hence it will be easier to manage and update any permission from the user

Let's have a Look 👀, How to achieve the above task by doing a hands-on session 💻

* To create a user group, follow the below command
    
    ```bash
     sudo useradd younus-devops -m #add user with directory present in home
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1679665891807/1787492d-e8e9-48dd-a292-f118d08008ab.png align="center")
    
    Hence you will be getting the output as the above image. Now the question arise, how do I switch to user younus-devops, hence setup the password of user
    
    ```bash
     sudo passwd younus-devops # sets password of user: younus-devops
     su younus-devops #change current user to younus-devops
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1679666313788/8bf57c42-ad43-4fe1-b26a-cfee9613c999.png align="center")
    
    you will be getting output same as above image shown
    
* To add multiple users or append the already existing user to a particular group, use the below command
    
    First we will create a group and later append user in it
    
    ```bash
    sudo groupadd devops #create user group devops
    sudo gpasswd -a younus-devops devops #append younus-devops to group devops
    sudo gpasswd -M younus-devops,younus-dev devops #add multiple user on the go
    ```
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1679666633161/a6668e65-2c7b-45dd-950f-67132e55fa5a.png align="center")

To view our newly create group and user we need to view the follow bellow command

```bash
sudo cat /etc/passwd #check the user info
sudo cat /etc/group #check the group and user add into it
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1679924483692/1e09b256-6863-4b53-89cc-c8c0938dd6e4.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1679924487038/791a77aa-f360-485d-b07d-ddddc3bf8539.png align="center")

# Understanding about "sudo" user

The sudoers file is **a file Linux and Unix administrators use to allocate system rights to system users**.

```bash
sudo vim /etc/sudoers #used to view admin permission
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1679924795494/6ea578f1-3844-4956-8abf-31d33e505096.png align="center")

If we see 'sudo' is a super do user which has the same properties like the root user in the present in the Linux.

We can add a new user to the same file to add up same permission like the root user

# Searching a Pattern in Linux

Grep, find & awk are some of the famous commands to find text or pattern in a given file or system

## Grep

grep stands for Global Regular Expression Pattern. It is used to search a pattern or group of words from a given text file. It is mostly used in finding the exact words in a file.

To search for a string in a file, use the following command:

```bash
#Syntax for grep command
grep "string" filename
#Syntax to find recursively in the directory
grep -r "string" directory
```

Example of Grep command

```bash
grep -i "devops" test.txt #used to search devops with ignore case sensitive
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1679925396038/55b5e840-1d5b-4753-a87f-67f6114bfdb5.png align="center")

## Find

`find` the command is used to search for files or directories in a specified location based on various criteria such as name, size, type, and time modified.

```bash
#To find all text files (ending with .txt) within the current directory and its subdirectories, use the following command:
find . -type f -name "*.txt"

#To find files modified within 24 hours, use the following command:
find . -type f -mtime -1
```

Example of find from above example

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1679925758057/6d8ff76e-2f26-49bf-9d88-8acb96227f2b.png align="center")

## AWK

`awk` stands for `Aho`, `Weinberger`, and `Kernighan` who created the language. `awk` is a versatile command-line tool for text processing, which can perform various operations like searching, finding and replacing, filtering, and more.

awk features user-defined functions, multiple input streams, TCP/IP networking access, and a rich set of regular expressions.

```bash
#To print a specific field (i.e, word or column) from a file, use the following command:
awk '{print $1}' filename

#To print lines starting with a particular character, use the following command:
awk '/^DevOps/' filename
```

Example of awk using the above command

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1679926164198/99fbdb1e-0d14-4d9b-97a1-0edb3e9ab78a.png align="center")

```bash
#Mainly AWK uses for tracing file
awk '{print $3}' tracefile.txt

awk '{print $4}' tracefile.txt

awk '/GET/{print $4}' tracefile.txt
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1679927249815/8cbbd0ec-af32-49d9-811b-7daa0fb3825d.png align="center")

These are some basic examples of `grep`, `find`, and `awk` commands in Linux. There are many more options available for these commands, and you can find them in the respective manuals (`man grep`, `man find`, `man awk`)

# Grant Permission to File or Groups

Give Permission to files or directories is been critical, especially when working within a large organization hence to manage the permission of the File and Group we are going to use the *chmod, chown, ACL*

## chmod

`chmod` stands for "change mode" and is used to change the permission modes on files and directories. There are three basic permission modes: read, write and execute, represented by the letters r, w, and x, respectively.

![chmod Cheatsheet : r/linux](https://preview.redd.it/vkxuqbatopk21.png?auto=webp&s=81f97dac1e1ceb5054ee43cbe96ec6fa55215695 align="left")

To give read, write and execute permission to the owner and group members of a file, use the following command:

> Tip: Just Remember read,write,execute number for giving absolute file permission

4 =&gt; Read Permisssion

2 =&gt; Write Permission

1 =&gt; Execute Permisssion

0 =&gt; No permission

```bash
#To give read, write and execute permission to the owner and group members of a file, use the following command:
chmod 770 filename
```

Here, 7 refers to read, write, and execute permission to the owner, 7 refers to read, write, and execute permission to the group members, and 0 refers to no permission to others.

If you run the above commands you will be getting corresponding output as follows

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1679926475715/03cf1237-4df5-4c20-9be4-ee3911b9762f.png align="center")

## chown

`chown` is short for "change owner" and is used to change the owner or group of a file or directory.

```bash
#To change the owner of a file to user1, use the following command:
sudo chown user1 filename

#To change both the owner and group of a file at the same time, use the following command:
sudo chown user1:user1group filename
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1679926633878/29cd3f7a-3610-49f5-954e-738c99be3e6f.png align="center")

## ACL - access control list

`acl` stands for "access control list" and allows you to grant permissions to individual users or groups for a specific file or directory beyond the basic permission modes set by `chmod`.

```bash
#To grant read and write permission to user1 on a specific file, use the following command:
setfacl -m u:user1:rw filename

#To grant read and execute permission to group1 on a specific directory, recursively, use the following command:
setfacl -R -m g:group1:rx directoryname

#TO get current permission of the file in a clean manner
#getfacl demo.txt
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1679927351600/9a314e27-b6e9-4751-93bf-92722c9241f2.png align="center")

```bash
#sets only read and write permission to devops group
setfacl --modify group:devops:rw demo.txt
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1679927502587/1878b593-a6d8-4118-860e-a2c1b44526a7.png align="center")

These are some examples of how you can use `chmod`, `chown`, and `acl` commands to grant permission to files and directories in Linux. However, it is crucial to use these commands carefully as incorrect usage can expose sensitive files to security threats.

# Understanding package manager commands and usage in Linux

## systemctl

`systemctl` is a command-line utility in Linux used to control the state of the `systemd` system and service manager. The `systemctl` command can be used to manage system services, start and stop services, manage system targets and check the status of system services.

Here are some commonly used `systemctl` commands in Linux:

### **1\. Start a service**

To start a service, use the following command:

```bash
sudo systemctl start service-name
```

Replace "service-name" with the actual name of the service you want to start.

### **2\. Stop a service**

To stop a running service, use the following command:

```bash
sudo systemctl stop service-name
```

Again, replace "service-name" with the actual name of the service you want to stop.

### **3\. Restart a service**

To restart a running service, use the following command:

```bash
sudo systemctl restart service-name
```

### **4\. Enable or disable a service at boot**

To enable a service to start automatically at boot, use the following command:

```bash
sudo systemctl enable service-name
```

To disable a service from starting automatically at boot, use the following command:

```bash
sudo systemctl disable service-name
```

### **5\. Check the status of a service**

To check the status of a running service, use the following command:

```bash
sudo systemctl status service-name
```

This command will show you whether a service is running, stopped, or has encountered any other issues.

### **6\. List all running services**

To list all the running services on your system, use the following command:

```bash
sudo systemctl list-units --type=service --state=running
```

These are some common `systemctl` commands in Linux that can help you manage system services and system targets. In summary, `systemctl` is an essential command-line utility that users can employ to manage system services and simplify their Linux experience.

# Conclusion

Great, Thank you for reading my blog post till the end! We have covered some advanced topics in Linux like connecting to a remote machine using SSH, creating users and adding them to groups, Granting File Permission, searching for patterns using grep, find, and awk commands, and understanding Systemctl and package manager commands This is a critical aspect of managing a Linux system, and it's something that you'll need to know as a DevOps engineer.

I would like to thank @[Shubham Londhe](@TrainWithShubham) for the amazing [**series on Linux**](https://www.youtube.com/watch?v=39oyFIStuaI&list=PLlfy9GnSVerQr-Se9JRE_tZJk3OUoHCkh). Do check it, if you are a beginner,

![giphy.gif](https://cdn.hashnode.com/res/hashnode/image/upload/v1664794453052/_OhviGh1R.gif?auto=format,compress&gif-q=60&format=webm&auto=format,compress&gif-q=60&format=webm&auto=format,compress&gif-q=60&format=webm align="left")

If you find my blog useful or need any suggestions to improve my blog, then Feel Free to connect with me on [**LinkedIn**](https://www.linkedin.com/in/younus-saberi/) and [**Twitter**](https://twitter.com/younussaberi) 🙌

And Until Next Time  
See you in the Cloud ☁️