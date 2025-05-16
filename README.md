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
 

 



# Systemcall Implementation  
