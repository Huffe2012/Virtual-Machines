# Virtual-Machines Set Up
🧪 Cybersecurity Lab Setup Summary

In this lesson, I created a personal cybersecurity lab using VirtualBox, featuring two virtual machines: a Windows 10 VM and an Ubuntu VM.

🖥️ Windows 10 VM – Used for simulating a target or victim system, useful for malware analysis, vulnerability testing, and practicing incident response.

🐧 Ubuntu VM – Configured as the attacker machine with various cybersecurity tools (e.g., Nmap, Wireshark, Metasploit) for penetration testing and ethical hacking practice.

This environment is ideal for learning, testing, and improving cybersecurity skills in a controlled and safe setting.
![Screenshot 2025-06-22 002606](https://github.com/user-attachments/assets/337d7f47-0f15-45b2-8936-af14e5f62f04)

**-Downloaded and Installed VirtualBox**
Used VirtualBox as the virtualization platform to host the virtual machine.

**-Downloaded Microsoft Windows ISO**
Obtained the official Microsoft ISO file to install as the guest operating system in the VM.
Note: Microsoft provides evaluation versions that allow free usage for testing and development.

**-Created Folder Structure**
Created a directory named SOC101 and added the ISO file to it for organization.

**-Launched Virtual Machine**
Imported the ISO file into VirtualBox and started the VM to begin the Windows installation process.

**-Resolved Errors**
Encountered error:
Hyper-V-VT-x is not available (VERR_VMX_NO_VMX)
Solution:
Disabled Hyper-V using the following command:

bcdedit /set hypervisorlaunchtype off

**-Installed Windows OS**
Proceeded with the Windows installation after resolving virtualization conflicts.

**-Created Snapshot**
Took a snapshot (Machine > Take Snapshot) post-installation in case a rollback is needed later.

## 🔐 Windows Defender Configuration
To simulate a more open threat environment for malware analysis and detection practice:

**Disabled Tamper Protection from Windows Security settings.**

Used PowerShell to disable several Defender features:


Set-MpPreference -DisableRealtimeMonitoring $true
Set-MpPreference -DisableIOAVProtection $true
Set-MpPreference -DisableScanningMappedNetworkDrivesForFullScan $true
Set-MpPreference -DisableBlockAtFirstSeen $true
Set-MpPreference -DisableAntiSpyware $true
## 📚 Lessons Learned
VirtualBox requires VT-x (Intel Virtualization) to be enabled.
Hyper-V conflicts with VirtualBox, so Hyper-V must be disabled to run VMs effectively.

Command Prompt must be run as Administrator when executing bcdedit or other system-level commands.
