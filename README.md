# CentOS-Stream-Server

# Main Documentation

[Introduction](#introduction)  
[Motivation](#Motivation)  
[Objectives](#objectives)  
[Requirements](#requirements)  
[Installation Steps](#installation-steps)  
[Issues](#issues)  
[Solutions](#solutions)  
[Filesystem](#filesystem)  
[Advantages and Disadvantages](#advantages-and-disadvantages)  
[Conclusion](#conclusion)  
[Future Outlook](#future-outlook)  
[Virtualization](#virtualization)  
## Introduction  
**Background**  

CentOS Stream Server is a Linux-based operating system developed as a continuously delivered distribution that sits between Fedora and Red Hat Enterprise Linux (RHEL) in the RHEL development process. It is maintained by the CentOS Project and backed by Red Hat.
CentOS Stream was introduced in 2019 as a rolling-release version of CentOS that tracks just ahead of a current RHEL release. This makes it particularly suitable for developers and system administrators who want to see what is coming in future versions of RHEL and contribute feedback upstream.
CentOS Stream Server is ideal for enterprise-grade applications, server hosting, and cloud infrastructure. It provides a stable, reliable, and secure platform that benefits from Red Hat’s development pipeline while also offering early access to updates and features. Its growing community and strong support for enterprise workloads make it a valuable tool in both educational and professional environments.  

## Motivation
My motivation for exploring CentOS Stream Server comes from its critical role in bridging the gap between upstream innovation and downstream stability in enterprise Linux systems. As the backbone of many production environments, understanding how CentOS Stream fits into the Red Hat ecosystem is valuable for anyone pursuing a career in systems administration, DevOps, or enterprise IT infrastructure.
CentOS Stream offers a unique opportunity to observe and interact with the development process of RHEL, providing insight into how features are integrated, tested, and stabilized. This makes it an excellent platform for learning about modern Linux server management, system updates, and deployment pipelines in a real-world context. Through this documentation, I hope to deepen my knowledge of enterprise-grade operating systems and better appreciate the workflow behind reliable Linux distributions.
 
## Objectives
•	To successfully install CentOS Stream Server in a virtual environment using Oracle VM VirtualBox  
•	To document the installation process thoroughly with detailed step-by-step instructions and relevant screenshots  
•	To explore and understand the key features of CentOS Stream Server, especially its rolling-release model and integration within the RHEL ecosystem  
•	To analyze the filesystem structure and supported filesystems in CentOS Stream Server  
•	To identify and address any challenges encountered during the installation or usage of CentOS Stream Server  
•	To implement and understand system calls (specifically kill() in the CentOS Stream Server environment)  
•	To evaluate the advantages and disadvantages of using CentOS Stream Server compared to other Linux-based operating systems  
•	To understand the concept of virtualization and how it is applied in modern operating systems using tools like VirtualBox  
•	To gain insights into Linux standardization and how CentOS Stream aligns with enterprise and community-driven development models  
## Requirements
**Hardware Requirements**  
•	Processor: 2 GHz dual-core processor or better  
•	RAM: Minimum 2 GB (4 GB or more recommended for optimal performance)  
•	Storage: At least 20 GB of free disk space  
•	Graphics: Any GPU capable of supporting standard virtual machine display  
•	Host System: Windows 10/11, macOS, or Linux with sufficient resources to run virtualization software  
**Software Requirements**  
•	Virtualization Software: Oracle VM VirtualBox (version 6.1 or later) or VMware Workstation (version 17 or later)  
•	Operating System ISO: CentOS Stream Server ISO (latest stable release from the official CentOS website)  
•	Internet Connection: Required for downloading the ISO and installing updates  
•	Optional Tools: Screenshot tool and image editing software (e.g., Snipping Tool, Paint, or GIMP) for documentation purposes  

## Installation Steps
 
✅ **Step 1:** Download Required Software and ISO Image  
**Objective:**  
Download and prepare all necessary files to start installing CentOS Stream Server on VirtualBox.  
**Instructions:**  
1.	Download and Install Oracle VM VirtualBox:  
•	Go to the official VirtualBox website: https://www.virtualbox.org/  
•	Click on "Downloads".  
•	Choose "Windows hosts".  
•	Once downloaded, run the installer and install VirtualBox with default settings.  
2.	Download CentOS Stream ISO:  
•	Visit: https://www.centos.org/centos-stream/  
•	Scroll down and click on “Get CentOS Stream”.  
•	Select "DVD ISO" under CentOS Stream 9 (or the latest version).  
•	Choose a mirror and download the ISO file (usually named like CentOS-Stream-9-latest-x86_64-dvd1.iso).  
✅ What You Should Have Now:  
•	VirtualBox installed on your Windows 11 PC.  
•	CentOS Stream ISO downloaded to your computer.  
 
![image](https://github.com/user-attachments/assets/d3767452-5178-46b7-ad54-7cfbcd490e8a)  


 ![image](https://github.com/user-attachments/assets/ac8202cf-a4af-44cd-84df-56a5a361d8ad)  
 
## ✅Step 2: Create a New Virtual Machine in VirtualBox  
**Objective:**  
Set up a virtual environment to install CentOS Stream Server.  
**Instructions:**    
**1.	Open VirtualBox** on your Windows 11 PC.  
**2.	Click on "New"** at the top-left corner.  
**3.	In the Name and Operating System window:**  
**o	Name:** CentOS Stream Server (or use your full name as instructed, e.g., John Doe CentOS Server)  
**o	Machine Folder:** Leave as default unless you want to change the storage location.  
**o	Type:** Linux  
**o	Version:** Red Hat (64-bit) (CentOS is derived from Red Hat)  
✅ Click **Next** after filling in the details.  
**4.	Memory Size:**  
o	Allocate at least 2048 MB (2 GB) of RAM (recommended: 4096 MB if your PC supports it).  
**✅ Click Next.**  
**5.	Hard Disk:**  
o	Select "Create a virtual hard disk now".  
**✅ Click Create.**  
**6.	Hard Disk File Type:**  
o	Choose VDI (VirtualBox Disk Image).  
**✅ Click Next.**  
**7.	Storage on Physical Hard Disk:**  
o	Select Dynamically allocated.  
**✅ Click Next.**  
**8.	File Location and Size:**  
o	Set size to at least 20 GB.  
**✅ Click Create.**  
 
 
**the virtual machine is now created**  

![image](https://github.com/user-attachments/assets/d5f4b771-1d0c-4175-8d18-5ce309ab8d90)  

![image](https://github.com/user-attachments/assets/c5922500-b496-4141-8ca4-bca206a6f2d9)


![image](https://github.com/user-attachments/assets/fd23fb76-085d-42c5-9348-6ac267f5780b)

## ✅ Step 3: Mount the CentOS Stream ISO and Start the VM  
**Objective:**  
Attach the CentOS Stream Server ISO file to the virtual machine and begin the installation process.  
**Instructions:**  
**1.	Select your new virtual machine** (e.g., CentOS Stream Server) in VirtualBox.  
2.	Click **"Settings"** on the top toolbar.  
3.	Go to the **"Storage"** tab in the left sidebar.  
4.	Under **"Storage Devices":**  
o	Click on **"Empty"** under the **Controller: IDE** section.  
o	On the right side, click the **CD icon** next to “Optical Drive”, then choose:  
**•	“Choose a disk file...”**  
•	Browse to and select the **CentOS Stream ISO** file you downloaded in Step 1.  
5.	Click **OK** to close the Settings window.  
6.	With the VM selected, click **"Start"** (green arrow) to boot from the ISO.  
 
**🔄 The virtual machine will now boot into the CentOS Stream installation screen.**  
![image](https://github.com/user-attachments/assets/08c7e610-a2f2-49f9-b413-d5f951a159d6)
![image](https://github.com/user-attachments/assets/1326f913-f6ba-48c5-8084-5cb3b1610eaa)

# Systemcall Implementation  
