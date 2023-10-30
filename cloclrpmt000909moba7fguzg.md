---
title: "Day 6: Linux Security Unveiled: Mastering File Permissions and Access Control Lists"
seoTitle: "Linux Security Unveiled: Mastering File Permissions and Access Control"
seoDescription: "File permissions in Linux play a crucial role in the realm of security and user management. They are a fundamental ....."
datePublished: Mon Oct 30 2023 07:53:01 GMT+0000 (Coordinated Universal Time)
cuid: cloclrpmt000909moba7fguzg
slug: day-6-linux-security-unveiled-mastering-file-permissions-and-access-control-lists
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1698651994969/fe8204af-b63e-453b-bec4-a0e7f95b7bae.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1698652334891/6ead71b4-9b6e-451b-94d7-03c1fa11a318.png
tags: devops, hashnode, 90daysofdevops, wemakedevs, trainwithshubham

---

### What is File Permission and why it is Important?

File permissions in Linux play a crucial role in the realm of security and user management. They are a fundamental component for controlling access, ensuring data privacy, and safeguarding against unauthorized use of files and directories. Understanding and effectively managing these permissions is a vital skill for Linux users, system administrators, and developers.

Linux file permissions revolve around the concepts of ownership and access levels. Each file and directory has an owner and group, with permissions assigned to dictate what actions can be performed by these entities. The permission system comprises three key elements: read, write, and execute permissions. These permissions can be configured separately for the file's owner, the group, and others.

This introduction lays the foundation for a deeper exploration of file permissions and access control in Linux, providing essential insights into managing and optimizing these crucial elements for a secure and customized Linux environment.

In my previous articles, I have mentioned that everything in Linux is either a file or a directory and in Linux you work in a multi-user environment, it is very crucial to know about the File Permissions of the Linux Operating System.

### How to Check File Permission?

If you know the basics of terminal in Linux then you might know how to list files with the Command Line Interface/Terminal (CLI). It is very similar to that.

If you don't know how to list files normally, It is done with the `ls` command

```bash
ls
```

* use the ls command in any directory and it will list all the contents in the directory. an example of that can be seen below.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698647084975/a854604f-7520-49e7-955a-ebdcffc9d3d3.png align="center")

You now know how to list files normally using CLI. Now let's see how you can list the files with their permissions.

### How to list File with Permission?

This can be done using a simple flag with the ls command which is -l (hyphen l). This will list the permission along with the contents present inside the directory.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698647276970/2a3f9579-bb05-4cf4-a52c-d77e41da7a24.png align="center")

Now you might be wondering what are those few things that are listed before the file names. Well, those are the permissions.

### Different types of Permissions

Permission comes in mainly 7 types and with those 7 types of permission, you can create many different combinations to control the users in the Linux OS.

* r-w-x = Read Write Execute
    
* r-w = Read Write
    
* r-x = Read Execute
    
* r = Read
    
* w-x = Write Execute
    
* w = Write
    
* x = Execute
    
* `blank` = No Permission
    

If you saw the above image carefully, you might have seen that in the second line, it contains

* `drwxrwxr` = here d stands for Directory
    

and the things which do not contain `d` are the files.

* rw-rw-r -- = here d is not present which means this is a normal file with read-write permission.
    

Now you know the basics of File Permissions in Linux and now let's move to the User group in the Linux Operating System.

### User Groups In Linux OS

User groups in the Linux operating system are a foundational element of user management and access control. They are essential for organizing users with similar privileges, facilitating efficient administration, and enhancing security. In Linux, each user belongs to one or more groups, and these groups play a pivotal role in determining file and directory access rights.

After reading the above paragraph you might be wondering about

the reader: why is he talking about different users ain't there a single user while we operate Linux?

Dipen: No! not here.

While starting this article I stated that While using Linux we work in a multi-user environment and that part comes under user groups in the Linux OS.

We will see the user group concerning file permissions that we have learned before to make it simple and easy to understand

File permissions are divided into 3 groups:

* owner — The owner of the file or application.
    
* group — The group that owns the file or application.
    
* others — All users with access to the system. (outside the users are in a group)
    

refer to this diagram below and the points written above 😆

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698649650941/a1ec1e12-c205-4930-b383-1570803a2c85.png align="center")

Look at the above image carefully and you'll see the various components of the user groups and the file permissions of the Linux OS

The first ( - ) dash at the beginning shows if the content is a file or a directory if the ( - ) is present then it is a file or if d is present instead of ( - ) then it is a directory. You'll see the example in the upcoming images.

* first -rw = means the Owner has the read-write permission
    
* second -rw = means the group has the read-write permission
    
* third -r = means the other group has only read permission
    

### User group permissions with chmod command

In the Linux OS, we use the chmod command to change the file permission wrt to the user groups

> "chmod" is used to change the other user's permissions of a file or directory.

* syntax of chmod:
    

```bash
chmod 777 filename.ext
```

look at the above code carefully,

* first 7 = for owner permission
    
* second 7 = for group permission
    
* third 7 = for other group permission
    

7 stands for `read-write-execute` permission in Linux to understand this further we will learn that with the image below

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698650639023/fc99e774-0fed-4e9f-aec9-e19d9e8bd9f1.png align="center")

### Chmod Number System in Linux

Chmod command in Linux is used to change the permissions of files and directories. multiple numbers are combined with the chmod command to change the permissions to our desire.

* 7 = read-write-execute
    
* 6 = read-write
    
* 5 = read-execute
    
* 4 = read
    
* 3 = write-execute
    
* 2 = write
    
* 1 = execute
    
* 0 = No permission
    

you can combine multiple numbers in groups of 3 with the chmod command to change the permissions of your desired groups.

### How To Check Your User?

To check your user in Linux you can use the cat command followed by the directory in which the user is. In Linux, the user is present in the etc directory.

```bash
sudo cat /etc/passwd
```

* etc/passwd is the directory which your user in
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698651336836/105a8968-4c37-40eb-b5d2-288720c45d41.png align="center")

* in this case, my username is sh, your username can be different than mine.
    

This was all about the File Permissions and User groups in Linux. Let me know if you have any doubts or you can post it in the comments.

Connect with me on:

Linkedin📎 : [https://www.linkedin.com/in/dipenr06/](https://www.linkedin.com/in/dipenr06/)  
Twitter📎 : [https://twitter.com/dipenr06](https://twitter.com/dipenr06)

Happy Learning💡

~Dipen : )