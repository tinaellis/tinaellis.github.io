<h2>Windows Registry</h2>
<a href="forensics">Back</a>
<p>Windows Registry is a binary hierarchical database used for storing configuration information for the computer hardware, OS configuration, programs, and user account and data. Almost all Microsoft applications use registry, however, software programs that are developed for multiple OS types do not use registry to store their program files.</p>
<p>Each time Windows boots, it builds a copy of registry that gets written to the memory.</p>
<b>Additional Resources</b>
<ul>
    <li><a href="https://techcult.com/what-is-windows-registry/" target="_blank">What is Windows Registry and how does it work</a></li>
    <li><a href="https://www.sans.org/posters/windows-forensic-analysis/" target="_blank">SANS Windows Artifact Analysis Poster Cheatsheet</a></li>
</ul>
<h2>Registry Structure and Hives</h2>
<p>The Windows Registry is made up of two basic elements called the Registry Key which is a container object or simply put they are like a folder that has various types of files stored in them and Registry Values which are non-container objects that are like files that could be of any format.</p>
<p>Using Registry Editor, we can see the 5 main Hives - “HKEY” is short for Hive Key.</p>
![Registry Editor](/assets/images/forensics-registry-hives.png)

<div class="intro">
    <h2>HKEY_CLASSES_ROOT Hive</h2>
</div>
<div class="steps">
    <h3>HKEY_CLASSES_ROOT</h3>
    <p>HKEY_CLASSES_ROOT stores information about registered applications, including associations from file extensions and OLE object class ID’s to the applications used to handle these items. This hive keeps track of file associations. For example, when you specify which program should run a specific application, this data is stored at this hive.</p>
</div>

<div class="intro">
    <h2>HKEY_CURRENT_USER Hive</h2>
</div>
<div class="steps">
    <h3>HKEY_CURRENT_USER</h3>
    <p>Abbreviated HKCU, the HKEY_CURRENT_USER stores settings that are specific to the currently logged-in user. The type of information that is stored is the same information that is found in HKEY_USERS, but specific to the currently logged-in user. The HKCU key is a link to the subkey of HKEY_USERS that corresponds to the user; the same information is accessible in both locations.</p>
    ![Registry Editor](/assets/images/registry-current-user.png)
    <b>Additional Resources</b>
    <ul>
        <li><b>Supported Files: </b>Ntuser.dat, Ntuser.dat.log</li>
    </ul>
</div>

<div class="intro">
    <h2>HKEY_USERS Hive</h2>
</div>
<div class="steps">
    <h3>HKEY_USERS</h3>
    <p>HKEY_USERS stores information about any user that has ever logged on to the machine. The data stored is broken up by SID’s (each user has a unique SID).</p>
    <b>Additional Resources</b>
    <ul>
        <li><b>Supported Files for HKEY_USERS\.DEFAULT: </b>Default, Default.log, Default.sav</li>
    </ul>
</div>

<div class="intro">
    <h2>HKEY_LOCAL_MACHINE and its subhives</h2>
</div>
<div class="steps">
    <h3>HKEY_LOCAL_MACHINE</h3>
    <p>Abbreviated HKLM, HKEY_LOCAL_MACHINE stores settings that are specific to the local computer. This includes hardware, software, OS, and application configuration data. The key located by HKLM is actually not stored on disk, but maintained in memory by the system kernel in order to map all other subkeys. Applications cannot create any additional subkeys. This key contains four subkeys, "SAM", "SECURITY", "SYSTEM", and "SOFTWARE", that are loaded at boot time within their respective files located in the %SystemRoot%\System32\config folder. A fifth subkey, "HARDWARE", is volatile and is created dynamically, and as such is not stored in a file (it exposes a view of all the currently detected Plug-n-Play devices).</p>
    <b>The four subkeys found within HKLM, are known as the four S’s.</b>
    <h3>SAM</h3>
    <p>The "HKLM\SAM" key is protected by the OS and usually appears empty when viewed with Registry Editor. It is used to reference all "Security Accounts Manager" (SAM) databases for all domains into which the local system has been administratively authorized or configured.</p>
    <p>Each SAM database contains all built-in accounts and configured accounts created and configured. Information stored here includes cryptographic hashes of each user's password for each enabled authentication protocol, the location of storage of their user registry hive, various status flags, and the list of domains in which the account was configured.</p>
    <p>The SAM file is located in the system at C:\WINDOWS\system32\config, and cannot be moved or copied when the OS is running.</p>
    <ul>
        <li><b>Supported Files: </b>Sam, Sam.log, Sam.sav</li>
    </ul>
    <h3>Security</h3>
    <p>The "HKLM\SECURITY" key is protected by the OS and usually appears empty when viewed with Registry Editor. The Security key is linked to the security database of the domain into which the current user is logged on. The kernel accesses this information and enforces the security policy applicable to the current user and all applications or operations executed by this user. It also contains a "SAM" subkey which is dynamically linked to the SAM database of the domain onto which the current user is logged on.</p>
    <ul>
        <li><b>Supported Files: </b>Security, Security.log, Security.sav</li>
    </ul>
    <h3>Software</h3>
    <p>The "HKLM\SOFTWARE" subkey contains software and Windows settings (in the default hardware profile). It is mostly modified by application and system installers. It is organized by software vendor (with a subkey for each), but also contains a "Windows" subkey for some settings of the Windows user interface, a "Classes" subkey containing all registered associations from file extensions, MIME types, Object Classes IDs, and interfaces IDs (for OLE, COM/DCOM and ActiveX), to the installed applications or DLLs that may be handling these types on the local machine (however these associations are configurable for each user), and a "Policies" subkey (also organized by vendor) for enforcing general usage policies on applications and system services (including the central certificates store used for authenticating, authorizing or disallowing remote systems or services running outside the local network domain).</p>
    <ul>
        <li><b>Supported Files: </b>Software, Software.log, Software.sav</li>
    </ul>
    <h3>System</h3>
    <p>The "HKLM\SYSTEM" key is normally only writable by users with administrative privileges on the local system. It contains information about the Windows system setup, data for the secure random number generator (RNG), the list of currently mounted devices containing a filesystem, several numbered "HKLM\SYSTEM\Control Sets" containing alternative configurations for system hardware drivers and services running on the local system (including the currently used one and a backup), a "HKLM\SYSTEM\Select" subkey containing the status of these Control Sets, and a "HKLM\SYSTEM\CurrentControlSet" which is dynamically linked at boot time to the Control Set which is currently used on the local system.</p>
    <ul>
        <li><b>Supported Files: </b>System, System.alt, System.log, System.sav</li>
    </ul>
</div>

<div class="intro">
    <h2>HKEY_CURRENT_CONFIG Hive</h2>
</div>
<div class="steps">
    <h3>HKEY_CURRENT_CONFIG</h3>
    <p>The HKEY_CURRENT_CONFIG hive stores the same information found in LOCAL_MACHINE but for what is currently going on in the system. HKEY_CURRENT_CONFIG contains information gathered at runtime; information stored in this key is not permanently stored on disk but rather regenerated at boot time and stored in memory.</p>
    <ul>
        <li><b>Supported Files: </b>System, System.alt, System.log, System.sav</li>
    </ul>
</div>