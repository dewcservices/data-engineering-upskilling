# Basics

This learning module will focus on the basics of software development. In this module, you will cover:

- Accessing virtual machines with SSH
- Shell 101
- Version control with Git
- crontab

## Accessing virtual machines with SSH

When working in Defence, we typically use Windows computers. While these computers are fine for common
Microsoft applications, they are not usually suitable for software development. We typically prefer
developing using the Linux operating system. However, you are unlikely to work directly on any physical
Linux computers when working in Defence. Instead, you are much more likely to remotely access a virtual
Linux machine.

The first step on your software development journey is to create a Linux virtual machine.

TODO: Add instructions to get a virtual machine.

## SSH

Now you have a machine, you are ready to use it!

First, open Windows terminal. Go to your search bar and search for `Terminal`. Next, type

```
ssh <VIRTUAL_MACHINE_ADDRESS>
```

At this point, you will be prompted for your password. Type in the password you created in the last section.
If all goes well, an SSH session will begin inside the terminal. You should now be able to run the following command:

```
lsb_release -i
```

, which should print `Distributor ID: Ubuntu`.




This guide assumes you already have access to a Linu

interact with locked-down Windows systems. Even in the DEWC office,
you typically login to a physical Windows machine that doesn't let you do very much unless you contact an
administrator.

When developing software, we usually want to develop on Linux-based systems

Typically, the machine you develop on is not the same as the physical machine that you 



