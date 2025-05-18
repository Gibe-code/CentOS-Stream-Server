

- **Operating System**: CentOS Stream Server  
- **Name**: Gebeyaw Derib  
- **Student ID**: BDU1601541  
- **Section**: B

---


# 📌 Quick Summary

## 🖥️ CentOS Stream Server Installation

CentOS Stream is a rolling-release Linux distribution positioned between Fedora and RHEL.  
To install CentOS Stream Server, begin by downloading the latest ISO image from the official CentOS website.  
Create a bootable USB drive using tools like Rufus or BalenaEtcher and boot your machine from it.  
Follow the guided installation steps, including disk partitioning, user creation, and software selection.  
Once installed, update the system and configure essential services like SSH, firewall, and package managers.

---

## ⚙️ System Call Implementation

System calls are the interface between user applications and the operating system kernel.  
In this project, I focused on implementing and analyzing the `lstat()` system call in a CentOS Stream environment.  
The `lstat()` system call retrieves file information without following symbolic links, unlike `stat()`.  
Implementation involves writing a C program that uses `lstat()` and compiling it within the Linux environment.  
Through this, I gained practical insights into kernel-user communication and low-level OS functionality.
