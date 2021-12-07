<h2>Creating Forensic Images</h2>
<a href="forensics">Back</a>

<h2>Memory Forensics</h2>
<p>Memory forensics is the process of capturing the running memory of< a device then analyzing the memory for evidence. Memory forensics is valuable during incident response when evidence of malicious code can still be found in the computer RAM. Memory dumps provide a snapshot of the memory which can be used to identify the running processes that were occurring when the capture was taken.</p>
<div class="intro">
    <h4>Capture a Memory Dump</h4>
<div>
<div class="steps">
    <b>Source Evidence Type:</b>
    <p>Volatile Memory, anything stored in RAM.</p>
    <h3>AccessData FTK Imager</h3>
    <ul>
        <li>Open AccessData FTK Imager</li>
        <li>File > Capture Memory</li>
        <li>Select the location where you want to save the output</li>
        <li>Select 'Capture Memory'</li>
    </ul>
</div>

<h2>Storage Forensics</h2>
<p>A forensics image created with FTK imager, is an identical copy of a hard-drive. This includes all of the data stored in sectors, partitions, files, folders, deleted files, unallocated spaces and master boot records.</p>

<div class="intro">
    <h4>Create a Forensics Image - FTK Imager</h4>
</div>

<div class="steps">
    <b>Source Evidence Type:</b>
    <p>Hardrives, Partitioned Drives (C: D: E:), Removable Storage, Folders, Files, CDs, and DVDs.</p>
    <h3>Creating a Forensics Image:</h3>
    <b>From FTK Imager:</b>
    <ul>
        <li>Open AccessData FTK Imager (You can run FTK Imager from a thumb drive (or a CD) to create a disk image or to image certain folders of a live system.)</li>
        <li>Create Disk Image</li>
        <li>Select Source (thumb drive = logical)</li>
        <li>Input case information</li>
        <li>Select save destination</li>
    </ul>
    <p>When FTK Imager finishes, a summary screen will appear that includes the hash digest information. After your analysis is completed, you can create a second hash digest to determine if the drive or file was changed during your forensics investigation.</p>
</div>

<div class="intro">
    <h4>Create a Forensics Image - NotMyFault</h4>
</div>

<div class="steps">
    <b>Source Evidence Type:</b>
    <p>Encrypted technologies such as Bitlocker drives. Can also be used with Hardrives, Partitioned Drives (C: D: E:), Removable Storage, Folders, Files, CDs, and DVDs.</p>
    <p>NotMyFault is a tool that can be downloaded directly from Microsoft. To create a memory dump from NotMyFault, you will need to tailor these instructions according to the Windows OS version you have installed. Here are the instructions for creating a Windows 7 memory dump.</p>
    <p><a href="https://docs.microsoft.com/en-us/sysinternals/downloads/notmyfault" target="_blank">Download NotMyFault from Microsoft</a></p>
    <h3>Part 1</h3>
    <p>Configure where your system failure files are saved:</p>
    <ul>
        <li>System Settings > Advanced > Startup and Recovery > Settings</li>
        <li>Under System Failure, select "Complete Memory Dump" or Kernel</li>
        <li>Check "Automatically Restart"</li>
    </ul>
    <h3>Part 2</h3>
    <p>From NotMyFault</p>
    <ul>
        <li>Go to folder where NotMyFault is downloaded > x64 > NotMyFault</li>
        <li>Select Crash</li>
    </ul>
    <p>This will crash your system and restart your computer. An image will be created and saved in the Settings file specified above. This method is useful when performing digital forensics on encrypted Bitlocker drives. To decrypt a Bitlocker drive, open the image file with a software tool such as Elcomsoft Forensic Disk Decryptor.</p>
</div>