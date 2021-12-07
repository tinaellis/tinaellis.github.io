## Creating Forensic Images
<a href="forensics">Back</a>

### Memory Forensics
Memory forensics is the process of capturing the running memory of a device then analyzing the memory for evidence. Memory forensics is valuable during incident response when evidence of malicious code can still be found in the computer RAM. Memory dumps provide a snapshot of the memory which can be used to identify the running processes that were occurring when the capture was taken.

**Source Evidence Type:**
Volatile Memory: anything stored in RAM.

**Capturing a Memory Dump:**
1. Open AccessData FTK Imager
2. File > Capture Memory
3. Select the location where you want to save the output
4. Select 'Capture Memory'

### Storage Forensics
A forensics image created with FTK imager, is an identical copy of a hard-drive. This includes all of the data stored in sectors, partitions, files, folders, deleted files, unallocated spaces and master boot records.

**Source Evidence Type:**
Hardrives, Partitioned Drives (C: D: E:), Removable Storage, Folders, Files, CDs, and DVDs.

**Creating a Forensics Image:**
**From FTK Imager:**
1. Open AccessData FTK Imager (You can run FTK Imager from a thumb drive (or a CD) to create a disk image or to image certain folders of a live system.)
2. Create Disk Image
3. Select Source (thumb drive = logical)
4. Input case information
5. Select save destination

When FTK Imager finishes, a summary screen will appear that includes the hash digest information. After your analysis is completed, you can create a second hash digest to determine if the drive or file was changed during your forensics investigation.

**From NotMyFault:**
NotMyFault is a tool that can be downloaded directly from Microsoft. To create a memory dump from NotMyFault, you will need to tailor these instructions according to the Windows OS version you have installed. Here are the instructions for creating a Windows 7 memory dump.

<a href="https://docs.microsoft.com/en-us/sysinternals/downloads/notmyfault" target="_blank">Download NotMyFault from Microsoft</a>

Configure where your system failure files are saved:
1. System Settings > Advanced > Startup and Recovery > Settings
2. Under System Failure, select "Complete Memory Dump" or Kernel
3. Check "Automatically Restart"

From NotMyFault
1. Go to folder where NotMyFault is downloaded > x64 > NotMyFault
2. Select Crash

This will crash your system and restart your computer. An image will be created and saved in the Settings file specified above. This method is useful when performing digital forensics on encrypted Bitlocker drives. To decrypt a Bitlocker drive, open the image file with a software tool such as Elcomsoft Forensic Disk Decryptor.