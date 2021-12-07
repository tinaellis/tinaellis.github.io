<h2>Creating Forensic Images</h2>
<a href="forensics">Back</a>

<h2>Memory Forensics</h2>
<p>Memory forensics is the process of capturing the running memory of< a device then analyzing the memory for evidence. Memory forensics is valuable during incident response when evidence of malicious code can still be found in the computer RAM. Memory dumps provide a snapshot of the memory which can be used to identify the running processes that were occurring when the capture was taken.</p>
<div class="steps">
    <h1>H1 Test</h1>
    <h2>H2 Test</h2>
    <h3>H3 Test</h3>
    <b>Source Evidence Type:</b>
    <p>Volatile Memory, anything stored in RAM.</p>
    <h3>Capturing a Memory Dump:</h3>
    <ul>
        <li>1. Open AccessData FTK Imager</li>
        <li>2. File > Capture Memory</li>
        <li>3. Select the location where you want to save the output</li>
        <li>4. Select 'Capture Memory'</li>
    </ul>

</div>

<h2>Storage Forensics</h2>
<p>A forensics image created with FTK imager, is an identical copy of a hard-drive. This includes all of the data stored in sectors, partitions, files, folders, deleted files, unallocated spaces and master boot records.</p>

<b>Source Evidence Type:</b>
<p>Hardrives, Partitioned Drives (C: D: E:), Removable Storage, Folders, Files, CDs, and DVDs.</p>

<h3>Creating a Forensics Image:</h3>
<b>From FTK Imager:</b>
<ul>
    <li>1. Open AccessData FTK Imager (You can run FTK Imager from a thumb drive (or a CD) to create a disk image or to image certain folders of a live system.)</li>
    <li>2. Create Disk Image</li>
    <li>3. Select Source (thumb drive = logical)</li>
    <li>4. Input case information</li>
    <li>5. Select save destination</li>
</ul>
<p>When FTK Imager finishes, a summary screen will appear that includes the hash digest information. After your analysis is completed, you can create a second hash digest to determine if the drive or file was changed during your forensics investigation.</p>

<b>From NotMyFault:<b>
<p>NotMyFault is a tool that can be downloaded directly from Microsoft. To create a memory dump from NotMyFault, you will need to tailor these instructions according to the Windows OS version you have installed. Here are the instructions for creating a Windows 7 memory dump.</p>

<p><a href="https://docs.microsoft.com/en-us/sysinternals/downloads/notmyfault" target="_blank">Download NotMyFault from Microsoft</a></p>

<p>Configure where your system failure files are saved:</p>
<ul>
    <li>1. System Settings > Advanced > Startup and Recovery > Settings</li>
    <li>2. Under System Failure, select "Complete Memory Dump" or Kernel</li>
    <li>3. Check "Automatically Restart"</li>
</ul>

<p>From NotMyFault</p>
<ul>
    <li>1. Go to folder where NotMyFault is downloaded > x64 > NotMyFault</li>
    <li>2. Select Crash</li>
</ul>

<p>This will crash your system and restart your computer. An image will be created and saved in the Settings file specified above. This method is useful when performing digital forensics on encrypted Bitlocker drives. To decrypt a Bitlocker drive, open the image file with a software tool such as Elcomsoft Forensic Disk Decryptor.</p>