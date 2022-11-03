# Ryzen-Hackintosh
``Hackintosh guide for Ryzen system.``

## **Getting started:**
Necessary things:
  + Al least 4GB USB stick
  + Time and patience
  + Know your hardware
  + A basic knowledge of command lines and how to use a terminal/command prompt
  + A machine that is compatible as seen in the `Compatibility` section in [Dortania's OpenCore guide](https://dortania.github.io/OpenCore-Install-Guide/)
  + An Ethernet connection (no WiFi dongles)

Creating the USB: (for Windows users)
  + Python 3.11: [Download](https://www.python.org/downloads/) 
  + OpenCorePKG: [Download](https://github.com/acidanthera/OpenCorePkg/releases) (download the `Release`)

I choose the Disk Management method
  + GUI based, simplest way
  + Only UEFI systems are supported (all Ryzen systems are UEFI)

Simply open up Disk Management, and format your USB as FAT32:
1. Right click the Start Button on your task bar and select Disk Management.
2. You should see all of your partitions and disks. On the bottom half, you'll see your devices. Find your USB.
3. You'll want to format the USB to have a FAT32 partition.
  + If you have multiple partitions on the USB, right click each partition and click Delete Volume for your USB (This will remove data, make sure you have backups and only remove partitions from your USB)

Right click the partition on the USB and click Format and set it to FAT32.

Next, go to the root of this USB drive and create a folder called `com.apple.recovery.boot`. Then move the downloaded BaseSystem or RecoveryImage files. Please ensure you copy over both the .dmg and .chunklist files to this folder:<img width="824" alt="com-recovery 805dc41f" src="https://user-images.githubusercontent.com/68218885/199646649-a2becebe-ae6c-4455-a367-3a80f5349e49.png">

Now grab OpenCorePkg you downloaded earlier and open it:
<img width="1010" alt="base-oc-folder 9a1a058a" src="https://user-images.githubusercontent.com/68218885/199646724-64e3e4a5-7291-483d-813a-c2b9e43961c3.png">

Choose the X64 files, and move it to your USB.
Once done it should look like this:
<img width="986" alt="com-efi-done a6fb730e" src="https://user-images.githubusercontent.com/68218885/199646835-579761ea-64ca-4cd0-8bf5-0c62d182eaef.png">

**Now with all these done, let's move on to the next section**

## **Adding the base OpenCore files and gathering files**
**Cleaning up the EFI:**

Lets open up our EFI folder and see what's inside:
<img width="1032" alt="base-efi 7500e22d" src="https://user-images.githubusercontent.com/68218885/199647323-76c0031f-b374-4d0f-ad19-fdfce289cf0a.png">

Delete all files in `Driver` and `Tools`, except `OpenRuntime.efi` and `OpenShell.efi`

Now you can place your necessary firmware drivers(.efi) into the `Drivers` folder and Kexts/ACPI into their respective folders.

**Reminder:**
  + SSDTs and custom DSDTs(.aml) go in ACPI folder
  + Kexts(.kext) go in Kexts folder
  + Firmware drivers(.efi) go in the Drivers folder
