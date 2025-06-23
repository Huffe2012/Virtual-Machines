# Virtual-Machines
🛠️ Setup Steps
Downloaded and Installed VirtualBox
Used VirtualBox as the virtualization platform to host the virtual machine.

Downloaded Microsoft Windows ISO
Obtained the official Microsoft ISO file to install as the guest operating system in the VM.
Note: Microsoft provides evaluation versions that allow free usage for testing and development.

Created Folder Structure
Created a directory named SOC101 and added the ISO file to it for organization.

Launched Virtual Machine
Imported the ISO file into VirtualBox and started the VM to begin the Windows installation process.

Resolved Errors
Encountered error:

csharp
Copy
Edit
Hyper-V-VT-x is not available (VERR_VMX_NO_VMX)
Solution:
Disabled Hyper-V using the following command in an elevated Command Prompt:

vbnet
Copy
Edit
bcdedit /set hypervisorlaunchtype off
Installed Windows OS
Proceeded with the Windows installation after resolving virtualization conflicts.

Created Snapshot
Took a snapshot (Machine > Take Snapshot) post-installation in case a rollback is needed later.

🔐 Windows Defender Configuration
To simulate a more open threat environment for malware analysis and detection practice:

Disabled Tamper Protection from Windows Security settings.

Used PowerShell to disable several Defender features:

powershell
Copy
Edit
Set-MpPreference -DisableRealtimeMonitoring $true
Set-MpPreference -DisableIOAVProtection $true
Set-MpPreference -DisableScanningMappedNetworkDrivesForFullScan $true
Set-MpPreference -DisableBlockAtFirstSeen $true
Set-MpPreference -DisableAntiSpyware $true
📚 Lessons Learned
VirtualBox requires VT-x (Intel Virtualization) to be enabled.
Hyper-V conflicts with VirtualBox, so Hyper-V must be disabled to run VMs effectively.

Command Prompt must be run as Administrator when executing bcdedit or other system-level commands.
