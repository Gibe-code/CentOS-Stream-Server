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
[Future Outlook and Recommendations](#future-outlook-and-Recommendations)  
[Virtualization in Modern Operating Systems](#Virtualization-in-Modern-Operating-Systems)  
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
 
 ** ✅Step 2: Create a New Virtual Machine in VirtualBox ** 
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

**✅ Step 3: Mount the CentOS Stream ISO and Start the VM**  
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

**✅ Step 4: Begin the OS Installation**  
**Objective:**  
Start the CentOS Stream installation from the boot menu and proceed to the graphical installer.  
**Instructions:** 
1.	After booting from the ISO, you will see the CentOS Stream boot menu.  
2.	Use the arrow keys to highlight:  
o	Install CentOS Stream 9 (or similar depending on the version)  
3.	Press Enter to begin the installation.  
4.	Wait a few moments for the CentOS graphical installer to load.  
5.	Once it loads, you will see a Welcome to CentOS Stream screen:  
o	Choose your language (e.g., English)  
o	Click Continue
![image](https://github.com/user-attachments/assets/1e0c557c-0232-4321-913e-aab09a0bc77a)

 
✅ I'm now inside the CentOS Stream installation summary window.  

**✅ Step 5: Configure Installation Settings**  
**Objective:**  
To set up key installation settings before starting the CentOS Stream installation.  
 
**🔧 Instructions:**
At the Installation Summary screen, you’ll see several options. You must configure the following:
 
**1. Installation Destination**  
1.	Click "Installation Destination".  
2.	Under Local Standard Disks, make sure the disk is selected (checked).  
3.	Choose Automatic for partitioning (unless you have a specific partitioning scheme).  
4.	Click Done (top-left corner) to return to the summary screen.  
 
**2. Root Password**  
1.	Click "Root Password".  
2.	Set a strong password for the root user.  
3.	Confirm the password.  
4.	Click Done (top-left).  
 
**3. User Creation (Use Your Full Name)**  
1.	Click "User Creation".  
2.	Fill the form as follows:  
**o	Full name:** Your full name (as per assignment instructions)
**o	Username:** (e.g., yourfirstname)
**o	Password:** Set and confirm a password
**o	Check the box** “Make this user administrator”
3.	Click **Done.**
 
**📌 Optional (if shown):**
**•	Software Selection:** Leave as default (Minimal Install) or select Server with GUI if you prefer a graphical interface.  
**•	Time & Date:** Set your region or enable Network Time if needed.  
 
**✅ Once all sections are marked as “Complete”, click “Begin Installation” to start installing CentOS Stream Server.**  
 
 ![image](https://github.com/user-attachments/assets/c5af382f-17a4-420b-b962-6fd59a2d0318)

![image](https://github.com/user-attachments/assets/41952aef-56aa-496e-b454-b1550fde7224)  

![image](https://github.com/user-attachments/assets/3d571c6e-7de6-4257-b85e-1c183e588678)

 ![image](https://github.com/user-attachments/assets/e550cc77-860e-4fde-b34d-4d945882f7b4) 
 
![image](https://github.com/user-attachments/assets/c67601fe-378d-47d1-a9f2-0ba6435f1643)

![image](https://github.com/user-attachments/assets/7287c6d8-5089-41bb-b29b-ff55d038fabd)

![image](https://github.com/user-attachments/assets/7f9e0753-f335-4b1d-9fe2-4c3fa2922449)

**✅ Step 6: Complete Installation & Reboot**
**Objective:**  
Wait for the installation to complete and reboot into your new CentOS Stream Server system.  
 
**🔧 Instructions:**
1.	After clicking “Begin Installation”, CentOS will begin copying files and installing the system.  
🕒 This may take a few minutes.  
2.	While installation is in progress, you will see messages like:  
o	“Installing software”  
o	“Writing network configuration”      
o	“Configuring user settings”  
3.	Once the installation is finished, you’ll see the message:  
“Installation complete. Remove the installation media and reboot your system.”  
4.	Click the “Reboot System” button.  
5.	If VirtualBox still has the ISO mounted, you may boot back into the installer again.  
**🛑 To prevent this:**  
**o	Before the VM restarts, go to:**  
•	Devices > Optical Drives > Remove Disk from Virtual Drive  
•	Then click Force Unmount if prompted.  
6.	The VM will reboot into your freshly installed CentOS Stream Server system.
   
 
✅ Once rebooted, you should see a login screen. Log in with the user account you created using your full name.
 
 ![image](https://github.com/user-attachments/assets/abd3308a-cb84-4da0-a0f7-c2d781f9c7c9)  
 
![image](https://github.com/user-attachments/assets/73e43871-785e-4560-a720-059441f3f523) 

 ![image](https://github.com/user-attachments/assets/43315434-7c2f-476c-bb98-bd9559daf3fc)

**✅ Step 7: Post-Installation Setup (System Update and Configuration)**
**Objective:**  
Update the system packages and perform basic configurations to ensure CentOS Stream Server runs smoothly.  
 
**🔧 Instructions:**  
**1. Log In**  
•	At the login screen, enter your username and password (the one you created during installation).  
 
**2. Open the Terminal**  
•	If you installed Server with GUI, you can open the Terminal from the applications menu.  
•	If it's a minimal install (no GUI), you’ll land directly in a text-based terminal after login.  
 
**3. Switch to Root (if needed)**  

•	Enter the root password when prompted.  
 
**4. Update the System**
Run the following command to update all packages:
dnf update -y
•	This will fetch and install the latest updates.
•	Wait until the update process completes.
 
**5. (Optional but Recommended) Reboot After Update
reboot**
 
✅ After reboot, your system will be up-to-date and ready for further use (like implementing system calls, managing services, etc.).  
 ![image](https://github.com/user-attachments/assets/2c62f9a6-e34c-4f4b-8d55-5a4996877342)
![Uploading image.png…]()

 
 
## Issues

**🔧 Problems Faced During Installation**

1. **Virtual Machine Display Resolution**  
   After installation, the CentOS Stream Server VM was stuck at a low resolution (1024x768) and did not resize automatically with the VirtualBox window. Full-screen mode also did not scale properly.

2. **Guest Additions Installation Failure**  
   Initial attempts to install VirtualBox Guest Additions failed due to missing kernel headers and development tools (`kernel-devel`, `gcc`, etc.), which are required for compiling kernel modules.

3. **Network Configuration Issues**  
   Although the network adapter appeared as connected in VirtualBox, the VM had no internet access due to incorrect network adapter settings (NAT vs. Bridged Mode mismatch).

4. **Software Package Download Errors**  
   During installation or update attempts, some packages failed to download due to mirror selection issues or DNS resolution failures, which interrupted the installation process.

5. **Partitioning Confusion**  
   During the manual partitioning step, some options (like setting up a custom LVM or separate `/home`) were not intuitive for beginners and could easily lead to partitioning errors.


## Solutions  
**Resolving Installation Issues**  
**1.	Virtual Machine Display Resolution**  
To fix the display issue, VirtualBox Guest Additions were installed after installing the necessary kernel packages. The following commands were run inside the CentOS VM:
sudo dnf groupinstall "Development Tools"  
sudo dnf install kernel-headers kernel-devel elfutils-libelf-devel  

Then, the Guest Additions ISO was mounted via the VirtualBox menu, and the script VBoxLinuxAdditions.run was executed:  
sudo ./VBoxLinuxAdditions.run  

After a reboot, dynamic resolution adjustment and full-screen mode worked correctly.  

**2.	Guest Additions Installation Failure**  
As above, the issue was resolved by ensuring all development tools and kernel headers were installed before running the Guest Additions script. It's important to match the installed kernel version with the kernel-devel package.  

**3.	Network Configuration Issues**  
The network issue was resolved by switching the VirtualBox adapter setting from NAT to Bridged Adapter, which allowed the VM to directly access the host network.  
 Additionally, DNS settings were verified using:  
cat /etc/resolv.conf  

and manually updated if necessary.  

**4.	Software Package Download Errors**  
These were resolved by switching to more reliable mirrors. Running the following command helped refresh repositories:  
sudo dnf clean all  
sudo dnf makecache  

Also, temporarily switching to a different mirror list in the /etc/yum.repos.d/ directory helped bypass connectivity issues.  

**5.	Partitioning Confusion**  
To avoid manual errors, the automatic partitioning option was selected during installation. For users wanting custom partitions, official CentOS documentation was referenced for guidance on using LVM and creating /home, /var, and /boot partitions  

   
   
 
## Filesystem  
**CentOS Stream Server Filesystem**  
By default, CentOS Stream Server uses the ext4 (Fourth Extended Filesystem) as its primary filesystem during installation. It is selected for its balance between stability, performance, and compatibility. Ext4 supports large volumes and files, journaling, and backward compatibility with ext3/ext2.  
**•	Default:** ext4  
**•	Why ext4:** It is mature, well-supported, has good performance, and is reliable for server environments.  

**Other Supported Filesystems**  

CentOS Stream also supports several other filesystems that can be configured manually or during advanced installations: 

**•	XFS:**  
o	Default for many RHEL/CentOS setups on enterprise-grade systems.  
o	High performance and excellent for handling large files and parallel I/O.  
o	Chosen in many server environments.  

**•	Btrfs** (via external repo or manual install):  
o	Modern filesystem with snapshot and subvolume support, but not officially supported by RHEL-based production environments.  
o	Suitable for experimentation.  

**•	vfat/FAT32:**  
o	Used for EFI boot partitions.  
o	Provides cross-platform compatibility.  

**•	NTFS (via ntfs-3g):**  
o	Read/write support available through additional packages.  
o	Used mostly for interoperability with Windows-formatted drives.  

**•	exFAT:**  
o	Supported via external packages.  
o	Useful for USB drives, but not recommended for system partitions.  

**•	ZFS:**  
o	Can be installed manually but not officially supported by CentOS/RHEL.  
o	Advanced features like data integrity verification and built-in RAID.  

**Conclusion on Filesystem Usage**  
For most CentOS Stream Server installations, XFS is typically the default and preferred option in enterprise environments due to its scalability and performance, although ext4 remains a solid choice for general use, especially in virtualized environments.  
 
 
## Advantages and Disadvantages  

**Advantages of CentOS Stream Server**

**1.	Rolling-Release Model (Stable Yet Upstream)**  
o	CentOS Stream offers a unique position between Fedora (bleeding edge) and RHEL (fully stable), giving users early access to upcoming enterprise features.  

**2.	RHEL Compatibility**  
o	Provides a close preview of future RHEL releases, making it ideal for developers and system administrators who want to stay ahead in the Red Hat ecosystem.

**3.	Enterprise-Ready Environment**  
o	Built on the foundations of RHEL, CentOS Stream inherits a strong, stable codebase suitable for server and cloud workloads.  

**4.	Strong Community and Documentation**  
o	Supported by Red Hat and a large open-source community with extensive guides, forums, and documentation.

**5.	Free and Open Source**  
o	No licensing fees, making it ideal for education, testing, and production environments without the cost burden.

**6.	SELinux and Security Features**  
o	Comes with Security-Enhanced Linux (SELinux) by default, adding robust access control and security.

**Disadvantages of CentOS Stream Server**

**1.	Not a Traditional Stable Release**  
o	Unlike classic CentOS, Stream receives frequent updates, which may introduce instability for users expecting a long-term, unchanging environment.

**2.	Limited Support for Desktop Use**  
o	CentOS Stream is server-oriented; it lacks user-friendly features out of the box for desktop users (e.g., multimedia codecs, GUI tools).

**3.	Fewer Third-Party Repositories**  
o	Compared to Ubuntu or Debian-based systems, CentOS has fewer easy-to-install third-party apps or PPAs.

**4.	Learning Curve**  
o	Manual configurations, SELinux, and package management via dnf can be challenging for beginners.

**5.	Guest Additions and Driver Issues in Virtual Environments**  
o	Installing tools like VirtualBox Guest Additions can require manual intervention and additional packages.
 
 
## Conclusion  
Throughout this project, I have gained substantial insight into **CentOS Stream Server** and its pivotal role in the Red Hat Enterprise Linux (RHEL) ecosystem. CentOS Stream serves as a rolling-release distribution that sits just ahead of RHEL, making it a valuable platform for developers and administrators who want to preview and contribute to future RHEL versions. The installation process in a virtual environment, specifically within VMware Workstation, was smooth and well-documented. Minor compatibility issues, such as screen resolution and network bridging, were resolved with straightforward configuration adjustments and the installation of VMware Tools.
CentOS Stream's design emphasizes **stability and controlled innovation**, offering a balance between cutting-edge features and enterprise-grade reliability. This unique positioning makes it particularly appealing for system administrators and developers seeking a testbed for pre-RHEL changes.The use of **ext4** as the default filesystem underscores CentOS Stream’s commitment to reliability and maturity, providing excellent performance and compatibility across a wide range of hardware and software environments. The support for additional filesystems like XFS and Btrfs adds flexibility for various enterprise needs.CentOS Stream’s tight integration with tools like dnf, SELinux, and systemd, along with its support for container platforms such as Podman and Docker, reinforces its role as a modern server operating system. It is well-suited for development, testing, and even production use in certain cases, particularly when long-term foresight into RHEL is needed. The implementation of system calls within CentOS Stream demonstrated its robust Linux foundation. The successful use of system-level programming, including manipulation of processes via system calls like setpgid, confirmed the system’s suitability for both user-level and low-level kernel interactions. In conclusion, **CentOS Stream Server** stands out as a strategic and practical choice for developers and administrators seeking to work closely with the evolution of enterprise Linux. It combines forward-looking development with a solid foundation, making it an excellent platform for both experimentation and structured learning in modern server environments.
 
 
## Future Outlook and Recommendations  
**Future Outlook**  

CentOS Stream is set to play an increasingly important role in the Linux ecosystem, particularly within enterprise and development environments. As Red Hat transitions away from traditional CentOS Linux to CentOS Stream, the distribution is positioned as the **upstream source for future RHEL releases**, providing a more transparent and collaborative development process.The continued evolution of CentOS Stream will likely bring more frequent updates, improved tooling, and broader hardware support. With its integration into CI/CD pipelines and containerized environments, CentOS Stream is expected to gain further adoption among DevOps teams and developers who need to anticipate changes in enterprise environments.In the future, tighter integration with cloud platforms and better support for edge computing and hybrid deployments may further expand CentOS Stream’s relevance. Its role as a **bridge between Fedora’s innovation and RHEL’s stability** ensures it will remain an important distribution for those involved in shaping the future of enterprise Linux.  

**Recommendations**  
**1.	For New Users:**   
Invest time in understanding the lifecycle differences between CentOS Stream and traditional distributions. Regular updates and minor version changes are part of the model, so adaptability is essential.  

**2.	For System Administrators:**  
Consider using CentOS Stream in development and staging environments to mirror the upcoming state of RHEL. This approach can help in anticipating compatibility issues and ensuring smoother transitions in production.  

**3.	For Educators and Students:**  
Leverage CentOS Stream for hands-on learning about enterprise Linux, system administration, and service configuration. Its upstream nature makes it ideal for teaching real-world skills aligned with RHEL systems.

**4.	For Developers:**  
Use CentOS Stream to test software against a rolling version of what will become RHEL. Contributing to CentOS Stream also provides an opportunity to influence enterprise Linux development directly.

**5.	Tooling and Automation:**  
Embrace automation tools like Ansible or Terraform with CentOS Stream to align with best practices in managing dynamic, scalable systems.

**6.	Virtualization and Cloud Readiness:**  
As virtualization becomes more central to infrastructure management, CentOS Stream should be tested and integrated into virtualized and containerized deployments early in the development lifecycle.   

In summary, CentOS Stream Server offers a strategic and adaptable platform for multiple user groups. With careful planning and proactive maintenance, it can serve as a valuable foundation for development, learning, and production in a forward-looking Linux ecosystem.
 
 
## Virtualization in Modern Operating Systems   
**What is Virtualization?**  

Virtualization is the process of creating a **virtual version of computing resources**, such as operating systems, servers, storage devices, or networks, by abstracting the hardware through software. In simpler terms, it allows multiple virtual machines (VMs) to run on a single physical system, each operating as if it were a separate, independent machine. Each virtual machine operates with its own **virtual CPU, memory, disk, and network interface**, all managed by a hypervisor, which serves as the intermediary between the host hardware and the guest systems.  
 
**Why Virtualization Matters?**  

Virtualization plays a critical role in modern IT infrastructure for several reasons:  

**1.	Resource Optimization:**  
It allows organizations to maximize the use of physical hardware by running multiple VMs on a single server, reducing waste and lowering costs.

**2.	Isolation and Security:**  
Virtual machines are isolated from one another, which improves system security and stability. A failure or attack on one VM does not affect others.

**3.	Scalability and Flexibility:**  
Virtual environments can be quickly scaled up or down based on demand. New VMs can be provisioned in minutes without needing new physical machines.

**4.	Testing and Development:**  
Developers can use virtualization to test applications across multiple OS environments without needing separate physical systems.

**5.	Disaster Recovery and Backup:**  
Virtual machines can be easily backed up and restored. Snapshots allow system states to be saved and reverted if needed.

**6.	Cloud Computing Foundation:**  
Virtualization is a key enabler of cloud platforms (e.g., AWS, Azure, GCP) that offer Infrastructure as a Service (IaaS).
 
**How Virtualization Works?**  

Virtualization is made possible through a key component known as the **hypervisor**, which manages and allocates hardware resources to VMs. There are two main types of hypervisors:  

**•	Type 1 (Bare-metal Hypervisor):**  
Runs directly on the host hardware. Examples include VMware ESXi, Microsoft Hyper-V, and KVM. These offer high performance and are used in enterprise environments.

**•	Type 2 (Hosted Hypervisor):**  
Runs on top of a host operating system. Examples include VMware Workstation and Oracle VM VirtualBox. These are typically used for personal or development environments.

Here's how virtualization works step by step:  
1.	The hypervisor creates a virtual layer over the hardware.  
2.	This layer simulates virtual hardware components (CPU, memory, storage, etc.).  
3.	Guest operating systems (like CentOS, Ubuntu, or Windows) are installed on these virtual machines as if they were running on physical machines.  
4.	The hypervisor manages scheduling, I/O requests, and memory allocation across the VMs.  
Advanced features like **hardware-assisted virtualization** (Intel VT-x, AMD-V) enhance performance by allowing the guest OS to run closer to native speeds.  
 
 
**Virtualization in CentOS Stream Server Context**  

CentOS Stream Server plays a significant role in virtualization environments, particularly for developers, sysadmins, and enterprises working within or alongside the Red Hat ecosystem. Its rolling-release nature makes it a **forward-looking platform** ideal for testing, building, and managing virtualized systems that will align with future RHEL versions.

**Virtualization Support in CentOS Stream**  

CentOS Stream comes equipped with robust support for virtualization technologies out of the box, including:  

**•	KVM (Kernel-based Virtual Machine)**  
– A full virtualization solution built into the Linux kernel, allowing CentOS to act as both a host and a guest operating system.

**•	QEMU**  
– Works with KVM to provide hardware emulation and device passthrough.

**•	libvirt**  
– A powerful toolkit and API used to manage KVM/QEMU virtual machines through command-line tools (virsh) or graphical interfaces like virt-manager.

**•	VirtIO Drivers**  
– Provides high-performance I/O for virtual disks and network interfaces.

**•	Cockpit**  
– A web-based GUI that includes modules for managing virtual machines on CentOS Stream, making it more accessible for those less comfortable with command-line management.

**Use Cases in CentOS Stream**  

**1.	Development & Testing:**  
Developers use CentOS Stream to build and test virtualized applications or services intended for future RHEL systems, ensuring compatibility and readiness.

**2.	Private Clouds:**  
CentOS Stream is often used as the base OS in virtualization clusters running tools like oVirt, OpenStack, or Proxmox due to its upstream alignment with RHEL.

**3.	Nested Virtualization:**  
CentOS Stream supports running VMs inside other VMs, which is useful for training, simulation, or advanced CI/CD pipelines.

**4.	Containerization Support:**  
While not virtualization in the traditional sense, CentOS Stream offers native tools like Podman and Buildah for lightweight, OS-level virtualization alternatives to full VMs.

**Advantages of Using CentOS Stream for Virtualization**  

**•	Stability with Innovation:** You get access to near-future RHEL updates in a stable form.  
**•	Enterprise-grade Tooling:** Features like SELinux, systemd, and advanced networking (bridges, bonds, VLANs) are supported and production-ready.  
**•	Community and Vendor Alignment:** Since CentOS Stream feeds into RHEL, it allows for contributions and testing that may directly impact the future of enterprise Linux.

# Systemcall Implementation  
