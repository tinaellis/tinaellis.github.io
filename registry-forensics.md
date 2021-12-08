<h2>Windows Registry Forensics</h2>
<a href="forensics">Back</a>
<p>The FTK forensics toolkit provides us with built-in reports that allow us to dig into the data stored in Windows Registry, without the OS interfering with our investigation.</p>
<div class="intro">
    <h3>View Registry Files with FTK Forensics Toolkit</h3>
</div>
<div class="steps">
    <h3>Generate FTK Forensics Report</h3>
    <ul>
        <li>Open FTK</li>
        <li>Select “Go directly to working in program” to skip startup</li>
        <li>File > Add Evidence</li>
        <li>Select Image</li>
        <li>Processes to Perform > Check “Registry Reports” > Uncheck everything else (unless items are needed in report)</li>
        <li>Select Next</li>
        <li>Add Evidence</li>
        <li>Select Next</li>
        <li>Finish</li>
        <li>Navigate to Tools > Select Registry Reports</li>
        <li>Select “Check All” and Ok</li>
        <li>Navigate to File > Report Wizard</li>
        <li>Leave defaults on each page (unless you need something specific)</li>
        <li>Report Location > Make sure “Include Registry Viewer reports” is checked</li>
        <li>Finish</li>
        <li>Select “Yes” to view the report</li>
    </ul>
    <h3>Navigating FTK Report</h3>
    <p>From Case Summary > Registry Report</p>
    <h4>SAM - Users Report</h4>
    <p>This report includes a list of users and their SID’s. SIDs of 500 are typically for administrators, 501 is for guests. SIDs that start in the 1000s are usually where the user IDs are.</p>
    <img src="/assets/images/1SAM.png" alt="SAM report">
    <h4>Summary Report Software - OS Version</h4>
    <p>This report provides us with information on the OS (or software selected). It includes information such as what company licensed the software, when it was installed, and current version.</p>
    <h4>Summary Report: System - Time Zone Settings</h4>
    <p>This should help you understand the time zone that the image was created in. It provides information based upon the time zone that is stored in UTC time.</p>
</div>
<h2>FTK Demo Limitations</h2>
<p>One limitation of the FTK demo program is that it only allows us to examine 5000 files. To limit the number of files that we are examining in FTK, we can pull out the items in Windows Registry that we want to focus on. This can be done using FTK Imager.</p>
<b>If file size limitation occurs in FTK - use this process to isolate registry files:</b>

<div class="intro">
    <h3>FTK Imager</h3>
</div>
<div class="steps">
    <h3>Exporting Registry Files with FTK Imager</h3>
    <ul>
        <li>Open AccessData FTK Imager</li>
        <li>File > Add Evidence Item</li>
        <li>Select Image</li>
        <li>Navigate to the folders and files you want to export in the evidence tree.</li>
        <li>Four S files are found in the config folder: Image > Partition > NONAME [NTFS] > Root > WINDOWS > system32 > config</li>
        <li>Hold down ctrl key to select multiple items + Right Click</li>
        <li>Export Files > Save</li>
    </ul>
    <p>When you grab the Four S folders and files, you also need to grab NTuser.dats.</p>
    <ul>
        <li>This can be found at Image > Partition > NONAME [NTFS] > Root > users ></li>
    </ul>
</div>

<div class="intro">
    <h3>AccessData Registry Viewer</h3>
</div>
<div class="steps">
    <h3>View Registry Files with AccessData Registry Viewer</h3>
    <p>AccessData Registry Viewer is a tool that we can use to navigate into files that Registry Editor protects us from viewing. It works as a replacement for RegEdit.</p>
    <ul>
        <li><b>Use FTK Imager first to export registry files from an image.</b></li>
        <li>Open Registry Viewer > No (to run in demo mode)</li>
        <li>Click Open (folder icon) > Browse and select Hive you want to open</li>
        <li>Double Click to open</li>
        <li>Expand tree (example) SAM > Domains > Account > Users</li>
    </ul>
</div>