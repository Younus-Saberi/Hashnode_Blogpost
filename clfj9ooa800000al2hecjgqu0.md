---
title: "Linux For DevOps"
datePublished: Wed Mar 22 2023 05:51:46 GMT+0000 (Coordinated Universal Time)
cuid: clfj9ooa800000al2hecjgqu0
slug: linux-for-devops
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1679461715537/83630d5a-8397-4b57-96fd-fce214a2e13a.jpeg
tags: linux, devops, 2articles1week, learning-journey, wemakedevs

---

# What is DevOps??

DevOps (a clipped compound of development and operations) is a culture, movement, or practice that emphasizes the collaboration and communication of both software developers and other information-technology (IT) professionals while automating the process of software delivery and infrastructure changes.

The main goal of DevOps is to deliver applications and services faster than usual methods and improve and evolve the products at a much brisker pace than software development organizations that are still stuck with traditional infrastructure management processes.

This ability to work at speed allows organizations to develop a much-needed competitive edge and at the same time, serve their customers in a better way.

### DevOps is culture and implemented in several phases with help of several tools.

Below is a GIF which explain DevOps very well

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1679464084638/088e3822-925a-40d9-96ab-66042b867aee.gif align="center")

To Begin our first step in DevOps, Linux will be a good choice to start off

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1679414303135/88bf1367-a3b1-4786-a66c-f96c14e166f9.jpeg align="center")

---

# Let's Learn about Linux

Now we are clear with the DevOps term and understood why the organization needs them. First and Foremost Good DevOps Engineers are the ones who are good at Linux and its core fundamentals knowledge

## What is Linux?

Just like Windows, iOS, and Mac OS, Linux is an operating system. In fact, one of the most popular platforms on the planet, Android, is powered by the Linux operating system. An operating system is a software that manages all of the hardware resources associated with your desktop or laptop.

To put it simply, the operating system manages the communication between your software and your hardware. Without the operating system (OS), the software wouldn’t function.

We are in an era where we cannot live without Linux/Unix systems. If you are an IT person or any undergraduate student you should know and have a better understanding and working knowledge of various Linux distributions highly used by organizations (RHEL, Ubuntu, Kali, etc.).

As per [The Linux foundation case study](https://www.linuxfoundation.org/projects/case-studies/), 90% of the public cloud workload runs on Linux.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1679416431380/9fa19872-2fa6-45e1-aef8-8bca63d6fd2c.webp align="left")

Now you have enough reasons why you should focus on Linux.

When it comes to Linux, it’s all terminal, GUI is less preferred. Get your hands dirty with the terminals of these systems.

> *TIP: The Best and Faster way to learn Linux is by using Linux or installing in it your local system*
> 
> You can use a [Virtual box](https://www.virtualbox.org/) with Ubuntu or use AWS/GCP/Azure to spin up Linux servers.

---

# Understanding Linux Architecture

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1679418042064/4a9ba378-c832-4bec-8b3a-2c8560290e84.jpeg align="left")

From the above diagram, you can an overview of the Linux architecture. It resembles live a Donut structure where the center part is the Hardware and the outermost part is the application layer

Computers only understand in form of Bits(0 or 1). Lets us understand how architecture works. Whenever the user writes a command in the terminal window, the shell will interpret the command and send it to the kernel. Kernel help to translate all the high-order commands given by the user into binary format. The data in terms send to hardware for performing the required task

> To summarise in short, Kernel plays an important role which acts as glue to combine the hardware of system with the software application running on the system
> 
> It is a computer program that is the core of a computer’s operating system, with complete control over everything in the system

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1679417419419/ef7e9554-6258-4c51-b4ba-34ae73b9f14c.png align="center")

---

# Linux Command Line Interface (CLI)

Let's get our hands dirty and learn the most common Linux commands. Before moving forward we need to understand the File Structuring System of Linux.

From the Below image, you can get a brief idea of how the directory and files are been arranged along with the commands to include in Linux by default and along with special files to keep running the operating system.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1679418203713/1e652ff5-474c-4877-aa87-d232589ba70c.png align="center")

---

# Basic Commands used in Linux

A Linux command is a program or utility that runs on the CLI – a console that interacts with the system via texts and processes

Here’s what a Linux command’s general syntax looks like:

```plaintext
CommandName [option(s)] [parameter(s)]
```

A command may contain an option or a parameter. In some cases, it can still run without them. These are the three most common parts of a command:

* **CommandName** is the rule that you want to perform.
    
* **Option** or **flag** modifies a command’s operation. To invoke it, use hyphens (**–**) or double hyphens (**—**).
    
* **The parameter** or **argument** specifies any necessary information for the command.
    

Keep in mind that all Linux commands are case-sensitive.

1. ### **ls command**
    
    The **ls** command lists files and directories within a system. Running it without a flag or parameter will show the current working directory’s content.
    
    To see other directories’ content, type **ls** followed by the desired path. For example, to view files in the **Documents** folder, enter:
    
    ```bash
    ls /home/username/Documents
    ```
    
    Here are some options you can use with the **ls** command:
    
    * **ls -R** lists all the files in the subdirectories.
        
    * **ls -a** shows hidden files in addition to the visible ones.
        
    * **ls -lh** shows the file sizes in easily readable formats, such as MB, GB, and TB
        
    
2. ### **touch command**
    
    The **touch command** allows you to create an empty file or generate and modify a timestamp in the Linux command line.
    
    For example, enter the following command to create an HTML file named **Web** in the **Documents** directory:
    

```bash
touch /home/username/Documents/Web.html
```

1. **Concatenate, or cat**  
    It is one of the most frequently used Linux commands. It lists, combines, and writes file content to the standard output. To run the cat command, type **cat** followed by the file name and its extension. For instance:
    
    ```bash
    cat filename.txt
    ```
    
    Here are other ways to use the [**cat command**](https://www.hostinger.in/tutorials/linux-cat-command-tutorial-and-examples/):
    
    * **cat &gt; filename.txt** creates a new file.
        
    * **cat filename1.txt filename2.txt &gt; filename3.txt** merges **filename1.txt** and **filename2.txt** and stores the output in **filename3.txt**.
        
    * **tac filename.txt** displays content in reverse order.
        
2. ### **mkdir command**
    
    Use the **mkdir** command to create one or multiple directories at once and set permissions for each of them. The user executing this command must have the privilege to make a new folder in the parent directory, or they may receive a permission denied error.
    
    Here’s the basic syntax:
    
    **mkdir \[option\] directory\_name**
    
    For example, you want to create a directory called **Music**:
    
    ```bash
    mkdir Music
    ```
    
    To make a new directory called **Songs** inside **Music**, use this command:
    
    ```bash
    mkdir Music/Songs
    ```
    
    The **mkdir** command accepts many options, such as:
    
    * **\-p** or **–parents** create a directory between two existing folders.  
        For example,
        
        ```bash
        mkdir -p Music/2020/Songs 
        #will make the new “2020” directory.
        ```
        
    * **\-m** sets the file permissions. For instance, to create a directory with full read, write, and execute permissions for all users, enter
        
        ```bash
        mkdir -m777 directory_name
        ```
        
    * **\-v** prints a message for each created directory.
        
    
3. ### **rm command**
    
    The **rm** command is used to delete files within a directory. Make sure that the user performing this command has write permissions.
    
    Remember the directory’s location as this will remove the file(s) and you can’t undo it.
    
    Here’s the general syntax:
    
    ```bash
    rm filename
    ```
    
    To remove multiple files, enter the following command:
    
    ```bash
    rm filename1 filename2 filename3
    ```
    
    Here are some acceptable options you can add:
    
    * **\-i** prompts system confirmation before deleting a file.
        
    * **\-f** allows the system to remove without a confirmation.
        
    * **\-r** deletes files and directories recursively.
        
    
4. ### **locate command**
    
    The [**locate command**](https://www.hostinger.in/tutorials/how-to-use-find-and-locate-commands-in-linux/) can find a file in the database system.
    
    Moreover, adding the **\-i** argument will turn off case sensitivity, so you can search for a file even if you don’t remember its exact name.
    
    To look for content that contains two or more words, use an asterisk (**\***). For example:
    
    ```bash
    locate -i school*note
    ```
    
    The command will search for files that contain the words **school** and **note**, whether they use uppercase or lowercase letters.
    
5. ### **df command**
    
    Use the [**df command**](https://www.hostinger.in/tutorials/vps/how-to-check-and-manage-disk-space-via-terminal) to report the system’s disk space usage, shown in percentage and kilobyte (KB). Here’s the general syntax:
    
    **df \[options\] \[file\]**
    
    For example, enter the following command if you want to see the current directory’s system disk space usage in a human-readable format:
    
    **df -h**
    
    These are some acceptable options to use:
    
    * **df -m** displays information on the file system usage in **MBs**.
        
    * **df -k** displays file system usage in **KBs**.
        
    * **df -T** shows the file system **type** in a new column.
        
    

---

### **Bonus Tips and Tricks**

Here are some tips and tricks you can use to manage the Linux system:

* Enter the **clear** or **Ctrl + L** command to clean the Terminal screen.
    
* Press the **Tab** button to autofill after entering a command with an argument.
    
* Use **Ctrl + C** to terminate a running command.
    
* Press **Ctrl + Z** to pause a working command.
    
* Use **Ctrl + S** to freeze your Terminal temporarily.
    
* Press **Ctrl + Q** to undo the Terminal freeze.
    
* Use **Ctrl + A** to move to the beginning of the line.
    
* Press **Ctrl + E** to bring you to the end of the line.
    
* You can use Up Arrow Key ↑ to go to previous commands executed
    

When executing multiple commands in a single line, use (**;**) to separate them. Alternatively, use **&&** to only allow the next command to run if the previous one is successful.

---

# Conclusion

In the end, Learning Linux and having Hands-on practice with it will be helpful to understand the core technology and fundamentals of the application, especially with respect to the cloud world.  
After learning basic Linux commands I will be posting about Shell Scripting which is basically a combination of various commands to perform task or automate a tedious task.

I would like to thank @[Shubham Londhe](@TrainWithShubham) for the amazing [series on Linux](https://www.youtube.com/watch?v=39oyFIStuaI&list=PLlfy9GnSVerQr-Se9JRE_tZJk3OUoHCkh). Do check it, if you are a beginner,

![giphy.gif](https://cdn.hashnode.com/res/hashnode/image/upload/v1664794453052/_OhviGh1R.gif?auto=format,compress&gif-q=60&format=webm&auto=format,compress&gif-q=60&format=webm align="center")

If you find my blog useful or need any suggestions to improve my blog, then Feel Free to connect with me on [**LinkedIn**](https://www.linkedin.com/in/younus-saberi/) and [**Twitter**](https://twitter.com/younussaberi) 🙌

And as Always  
See you in the Cloud ☁️