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
    <p>Hard drives, Partitioned Drives (C: D: E:), Removable Storage, Folders, Files, CDs, and DVDs.</p>
    <h3>Steps for Creating a Forensics Image:</h3>
    <b>From FTK Imager:</b>
    <ul>
        <li>Open AccessData FTK Imager (You can run FTK Imager from a thumb drive (or a CD) to create a disk image or to image certain folders of a live system.)</li>
        <li>Create Disk Image</li>
        <li>Select Source <em>see notes below</em></li>
        <li>Select Finish</li>
        <li>Image Destination > Select Add..</li>
        <li>Select Raw (dd) <em>see notes below</em></li>
        <li>Input Case Information</li>
        <li>Select the Save Destination Folder</li>
        <li>Input Filename</li>
        <li>Select Finish</li>
    </ul>
    <p>When FTK Imager finishes, a summary screen will appear that includes the hash digest information. After your analysis is completed, you can create a second hash digest to determine if the drive or file was changed during your forensics investigation.</p>
    <b>Image Source Options</b>
    <ul>
        <li>Physical Drive: <em>physical hard drives</em></li>
        <li>Logical Drive: <em>logical (partitions)</em></li>
        <li>Image File</li>
        <li>Contents of Folder</li>
        <li>Fernico Device: <em>CDs/DVDs</em></li>
    </ul>
    <b>Image Type Explanation</b>
    <ul>
        <li>Raw (dd): Image format most commonly used by modern analysis tools. Raw file is not compressed / format keeps data integrity.</li>
        <li>SMART: This format is designed for Linux file systems. Keeps disk image as pure bitstreams with optional compression.</li>
        <li>E01: This format is proprietary to EnCase. Compresses the image. Adds header with case information.</li>
        <li>AFF: Format doesn't lock user into proprietary format which might prevent analysis.</li>
    </ul>
</div>

<div class="intro">
    <h4>Create a Forensics Image - NotMyFault</h4>
</div>

<div class="steps">
    <b>Source Evidence Type:</b>
    <p>Encrypted technologies such as Bitlocker drives. Can also be used with Hardrives, Partitioned Drives (C: D: E:), Removable Storage, Folders, Files, CDs, and DVDs.</p>
    <p><a href="https://docs.microsoft.com/en-us/sysinternals/downloads/notmyfault" target="_blank">Download NotMyFault from Microsoft</a></p>
    <h3>Steps for Creating a Forensics Image:</h3>
    <b>From System Settings</b>
    <p>Configure where your system failure files are saved:</p>
    <ul>
        <li>System Settings > Advanced > Startup and Recovery > Settings</li>
        <li>Under System Failure, select "Complete Memory Dump" or Kernel</li>
        <li>Check "Automatically Restart"</li>
    </ul>
    <b>From NotMyFault</b>
    <ul>
        <li>Go to folder where NotMyFault is downloaded > x64 > NotMyFault</li>
        <li>Select Crash</li>
    </ul>
    <p>This will crash your system and restart your computer. An image will be created and saved in the Settings file specified above. This method is useful when performing digital forensics on encrypted Bitlocker drives. To decrypt a Bitlocker drive, open the image file with a software tool such as Elcomsoft Forensic Disk Decryptor.</p>
    <p><em>NotMyFault is a tool that can be downloaded directly from Microsoft. To create a memory dump from NotMyFault, you will need to tailor these instructions according to the Windows OS version you have installed. Here are the instructions for creating a Windows 7 memory dump.</em></p>
</div>