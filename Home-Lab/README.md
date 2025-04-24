# 🛡️ Setting Up a Cybersecurity Lab on an Old Laptop (8GB RAM)

I turned my old Acer Aspire laptop (with just 8 GB RAM and a 1TB HDD) into a lightweight cybersecurity lab. It is running Linux Mint as the host OS, with Kali Linux and Metasploitable 2 running as VMs inside VirtualBox.

## 🔧 Specs
Laptop: Acer Aspire (older model, purchased in 2014 with Windows 8.1 on it, and it was slow AF.)

RAM: 8 GB

Disk: 1 TB HDD

Host OS: Linux Mint XFCE

Virtualization: VirtualBox

## 🧱 Host OS Installation (Linux Mint)
1. Backed up anything I wanted from Windows 8.1 (this laptop's original OS).

2. Created a bootable USB using Rufus and the Linux Mint ISO.

3. Booted into the USB and chose "Erase disk and install Linux Mint".

4. Set up user account and system preferences.

5. Updated the system:

`sudo apt update && sudo apt upgrade -y`

(It is noticeably faster now. This is the primary reason I installed Linux.)
## 📦 Installing VirtualBox on Linux Mint

`sudo apt install virtualbox`

Also downloaded the VirtualBox Extension Pack from the Ubuntu Software Center.

## 🐱‍💻 Kali Linux VM Setup
1. Downloaded the Kali .7z VM image from Kali Linux official downloads.

2. Extracted the .7z archive using 7-Zip.

3. Tried to import the .ova file into VirtualBox:

    - File > Import Appliance > Select .ova file --> FAILED. (The file would not show up in the dialog box.)
  
    - Tried to drag and drop the file into VirtualBox --> SUCCESS!

6. Set network to Internal Network:

    - Settings > Network > Adapter 1 > Attached to: Internal Network

5. Gave it a name

**Default login:**

*Username:* kali

*Password:* kali

## 💣 Metasploitable 2 VM Setup
1. Downloaded from: https://sourceforge.net/projects/metasploitable/files/Metasploitable2/

2. Extracted the .zip archive to get Metasploitable.vmdk

3. In VirtualBox:

  - Created a new VM (Linux > Ubuntu 32-bit)

  - Set RAM to 768 MB

  - Used existing virtual hard disk and pointed to the Metasploitable.vmdk

  - Set the network to the same Internal Network as Kali (cyberlab)

**Default login:**

*Username:* msfadmin

*Password:* msfadmin

## 🌐 Checking Connectivity Between Kali and Metasploitable

From Kali's Terminal:
1. Found Kali’s IP in the internal network

`ip addr`        

2. Checked if I can reach the target

`ping <Metasploitable IP> `

Metasploitable also gets its IP via DHCP on boot — you can log in and run:

`ifconfig`

## 🔥 Ready to Hack (Ethically)

Now I can practice:

- Scanning (nmap, netdiscover)

- Exploitation (Metasploit)

- Vulnerability analysis

- Web app pentesting (DVWA, WebDAV, etc. on Metasploitable)

All offline, local, and safe.

## 💡 Lessons Learned

Lightweight Linux hosts (like Mint or XFCE-based distros) are amazing for old laptops.

You don’t need a fancy rig to build a home lab. So far, everything I have done was free, outside the initial laptop purchase, and my home wi-fi bill.

TIP: Always check .vmdk vs .ova — not all VMs import the same way.
