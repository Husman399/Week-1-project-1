# Week-1-project-1
project-1
Kali Linux VirtualBox Setup & Network Fix
https://link-to-your-first-image/
(Replace link-to-your-first-image with the actual link to the uploaded image in your repo)

📝 Overview
This repository documents the setup, configuration, and network troubleshooting of a Kali Linux virtual machine running on Oracle VirtualBox. It includes the specific VM hardware allocations and the command-line fix used to resolve network connectivity/DHCP timeout issues within the VM.

⚙️ Virtual Machine Specifications
Based on the VirtualBox configuration:

Name: kali linux

Operating System: Debian (64-bit)

Base Memory (RAM): 2048 MB (2 GB)

Processors: 2 CPUs

Video Memory: 16 MB (VMSVGA Controller)

Storage: 20.00 GB (VDI, dynamically allocated/normal)

Network Adapter: Intel PRO/1000 MT Desktop (NAT Network)

🌐 Network Configuration
The VM is configured to use a NAT Network in VirtualBox to allow internet access and communication between VMs.

Network Name: NatNetwork

IPv4 Prefix: 10.0.2.0/24

DHCP Server: Enabled

(See Image 3 in the repo for the VirtualBox NAT Network settings).

🛠️ Troubleshooting: Network Connectivity Fix
If the Kali Linux VM takes a long time to connect to the internet or fails to acquire an IP address, it may be due to the IPv4 Duplicate Address Detection (DAD) taking too long.

To resolve this, run the following command in the Kali terminal:

bash
sudo nmcli connection modify "Wired connection 1" ipv4.dad-timeout 0
What this does:
This sets the Duplicate Address Detection timeout to 0 for the wired connection, bypassing the delay and allowing the VM to connect to the network immediately.

Verifying the Connection
After running the command, you can verify the connection is active by:

Opening the Network Connections GUI to ensure "Wired connection 1" is active (as seen in the screenshots).

Opening the Firefox browser and navigating to google.com to confirm internet access.

🚀 Getting Started
Download and install Oracle VirtualBox.

Download the Kali Linux VirtualBox Image.

Import the .ova or .vdi file into VirtualBox.

Adjust the settings (RAM, CPUs, Network) to match the specifications above.

Boot the VM and apply the network fix if necessary.
