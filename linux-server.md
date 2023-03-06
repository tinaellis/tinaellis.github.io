## Server Basics
<a href="linux">Back</a>

<div class="intro">
    <h3>Services and Daemons</h3>
</div>
<div class="steps">
    <table>
        <tr>
            <th>Process</th>
            <th>Description</th>
        </tr>
        <tr>
            <td>Services</td>
            <td>Must always be ready for use and have little direct user interaction (Web servers, LDAP, SMTP, DHCP, etc)</td>
        </tr>
        <tr>
            <td>User Application</td>
            <td>Started and stopped by user with heavy user interaction (Word, Adobe Suite, etc)</td>
        </tr>
        <tr>
            <td>Daemons</td>
            <td>System daemon - the process that controls processes that are not initiated by a user. If a process is a service (daemon), the name typically ends with a d. <li>Web server - httpd</li>
            <li>FTP server - ftpd</li>
            <li>Mail Server - smtpd</li>
            <li>System Service - systemd</li></td>
        </tr>
        <tr>
            <td>init</td>
            <td>Init around since the beginning of UNIX, starts processes sequentially - can contribute to slow boot times</td>
        </tr>
        <tr>
            <td>systemd</td>
            <td>Loads processes in parallel - results in faster load time (than init).</td>
        </tr>
        <tr>
            <td>PID</td>
            <td>Process ID - Gives you some idea of when the process was loaded. Every process is assigned an id number when its started (every time one is assigned it’s incremented)</td>
        </tr>
        <tr>
            <td>Service Order</td>
            <td><p>1. Linux OS Kernel Process</p>
                <p>2. Instructions & Data</p>
                <p>3. Systemd (or init) Process</p>
                <p>4. Instructions & Data</p></td>
        </tr>
        <tr>
            <td>ps</td>
            <td>See the processes you are running</td>
        </tr>
        <tr>
            <td>ps -aux</td>
            <td>Shows all of the running processes. Problem is that this shows too much information, remedy is to use ps tree:</td>
        </tr>
        <tr>
            <td>pstree</td>
            <td>Allows you to see how the services were started and which service started it.</td>
        </tr>
        <tr>
            <td>yum install psmisc</td>
            <td>Use to install ps tree. Note it is part of misc package.</td>
        </tr>
    </table>
</div>
<div class="intro">
    <h3>systemctl</h3>
</div>
<div class="steps">
    <table>
    <p>Viewing services with systemctl.</p>
        <tr>
            <th>Command</th>
            <th>Description</th>
        </tr>
        <tr>
            <td>systemctl</td>
            <td>See list of services being managed by systemd. Shows both active services and everything systemd could possibly control, including services disabled or shutdown.</td>
        </tr>
        <tr>
            <td><p>systemctl list-units --type=service</p><p>| grep running | more</p></td>
            <td>See list of system d units that are of type=service (so just services) excludes disk and other devices . Pipe through grep to see currently running services.</td>
        </tr>
        <tr>
            <td>yum install openssh-server</td>
            <td>Install sshd daemon</td>
        </tr>
        <tr>
            <td>systemctl start serviceName</td>
            <td>To start a service</td>
        </tr>
        <tr>
            <td>systemctl start serviceName.service</td>
            <td>To specify the name of the configuration file. But not required. Leave the .service off and systemctl will still find the correct file</td>
        </tr>
        <tr>
            <td>systemctl stop serviceName</td>
            <td>Stops the service</td>
        </tr>
        <tr>
            <td>systemctl status serviceName</td>
            <td>Service status (If it is active/running, PID, Last few lines of services log file)</td>
        </tr>
        <tr>
            <td>yum remove serviceName</td>
            <td>Uninstall service. Example: yum remove openssh-server</td>
        </tr>
        <tr>
            <td>systemctl restart serviceName</td>
            <td>Restarting service. Most of the time when you make changes to a daemon configuration file, you need to restart it to read the changes</td>
        </tr>
        <tr>
            <td>systemctl reload serviceName</td>
            <td>Alternative to restarting the service. Tells the service to reread its configuration commands.</td>
        </tr>
        <tr>
            <td>systemctl enable serviceName</td>
            <td>Enables the Service - Configures a service to start automatically when the system starts. Starting a service doesn't configure it to start at boot, it will only run until the system shuts down</td>
        </tr>
        <tr>
            <td>systemctl enable serviceName --now</td>
            <td>Enable doesn’t start the service - you can start it by using --now</td>
        </tr>
        <tr>
            <td>systemctl disable serviceName</td>
            <td>Disables service.</td>
        </tr>
    </table>
</div>
<div class="intro">
    <h3>systemctl</h3>
</div>
<div class="steps">
    <table>
        <p>How systemd uses .service files to manage services. The system uses this information to determine which services to start and at what time.</p>
        <tr>
            <th>Service</th>
            <th>Description</th>
        </tr>
        <tr>
            <td>Unit File</td>
            <td>Special configuration file that each service must have</td>
        </tr>
        <tr>
            <td>Unit</td>
            <td>Each thing systemd controls is called a unit. Content of the unit file will vary depending on type.</td>
        </tr>
        <tr>
            <td>ls /lib/systemd/system | more</td>
            <td>Shows a list of unit files</td>
        </tr>
        <tr>
            <td>Unit Service File</td>
            <td>Divided into 3 main sections:
            <li>Unit Section</li>
            <li>Service Section</li>
            <li>Install Section</li>
            Each section will have specific parameters used to configure the service read by systemd.
            </td>
        </tr>
        <tr>
            <td>systemctl show ServiceName</td>
            <td>To see all of the parameters used by a service</td>
        </tr>
        <tr>
            <td>systemctl start sshd</td>
            <td>Running the start command initiates the search process.             
            <p>Looks in the following directories for the unit file, starting with the /etc/ directory and so on. It stops searching once the file is found.</p>
            <li>/etc/systemd/system</li>
            <li>/run/systemd/system</li>
            <li>usr/lib/sysemd/system</li></td>
        </tr>
        <tr>
            <td>Enabled Services - start automatically at boot</td>
            <td>systemd keeps track of the services you want to start automatically by creating a symbolic link (a shortcut) to each services .services unit file in the following directory:
            <li>/etc/systemd/system/multi-user.target.wants</li>
            <li>systemd knows which directory to put the symbolic link in by looking at what is specified in the WantedBy parameter in the Install section of the .services unit file.</li></td>
        </tr>
        <tr>
            <td>Symbolic Links</td>
            <td>These are like shortcuts in windows. Syntax for symbolic link in Linux: linkName -> actualFileName</td>
        </tr>
    </table>
</div>
<div class="intro">
    <h3>Firewalls</h3>
</div>
<div class="steps">
    <table>
        <tr>
            <th>Command</th>
            <th>Description</th>
        </tr>
        <tr>
            <td>
            <p>yum install firewalld</p>
            <p>systemctl enable firewalld</p>
            </td>
            <td>Install firewall package</td>
        </tr>
        <tr>
            <td>
            <p>systemctl status firewalld</p>
            <p>firewall-cmd --state</p>
            </td>
            <td><p>Checking current status and settings</p>
            <p>Checking whether firewalld is running</p></td>
        </tr>
        <tr>
            <td>firewall-cmd --get-zones</td>
            <td>Displaying all available zones</td>
        </tr>
        <tr>
            <td>firewall-cmd --get-default-zone</td>
            <td>Displaying the default zone (probably public). Default zone versus Active zone. The default zone will be active when system boots. The Active zone is the currently active zone for interface. This will be the default zone unless you explicitly change it.</td>
        </tr>
        <tr>
            <td>firewall-cmd --get-active-zone</td>
            <td>Displaying active zone (probably public)</td>
        </tr>
        <tr>
            <td>--get-active-zone or --get-default-zones</td>
            <td>Two special zones (default, and active). Default - when we start the firewall daemon what zone is it setto use. Active - if you travel and want to change this</td>
        </tr>
    </table>
</div>

<p>By default, firewalld comes with the following zones:</p>
<ul>
    <li>public: This is default zone, and it should be used for public environments where you do not trust other computers on the network. Only predefined connections (i.e. ports / services) are accepted.</li>
    <li>work: For work environments. Usually, other computers are trusted on the same network. Only predefined connections are accepted.</li>
    <li>home: For home use. The same applies as in the ‘work’ zone. Depending on your situation, the connections at work may be more secure than on your home network.</li>
    <li>internal: For use with private networks. Computers on this network are usually trusted. Only predefined connections are accepted.</li>
    <li>trusted: All connections are accepted.</li>
    drop: All incoming connections are rejected however outgoing connections are possible.
    <li>block: Like drop except incoming connections are denied with a message. This message varies by the type of incoming connection. For IPv4, the message is icmp-host-prohibited and for IPv6 icmp6-adm-prohibited. Outgoing connections are possible.</li>
    <li>external: This is used when your firewall is external to your DMZ or internal network, and works as a gateway with NAT masquerading. In this case you don’t trust other computers on the external network and only preconfigured connections are accepted.</li>
    <li>dmz: The computer is in the demilitarized zone. It should be isolated from the internal network so only specific connections should be accepted.</li>
</ul>


<div class="intro">
    <h3>Firewalls</h3>
</div>
<div class="steps">
    <table>
        <p>Firewall Adding and Removing Services, Permanent vs. Runtime Configuration Changes</p>
        <tr>
            <th>Command</th>
            <th>Description</th>
        </tr>
        <tr>
            <td>firewall-cmd</td>
            <td>Check status, change rules, etc</td>
        </tr>
        <tr>
            <td>firewall-cmd --state</td>
            <td>Check if firewall is running</td>
        </tr>
        <tr>
            <td>firewall-cmd --get-zones</td>
            <td>Out of the box, here are the different zones that have files associated with them.</td>
        </tr>
        <tr>
            <td>firewall-cmd --get-services</td>
            <td>Data files associate a protocol name with a port number, shows out of box services we can allow</td>
        </tr>
        <tr>
            <td>firewall-cmd --list-services</td>
            <td>In my current setting, what is being allowed through</td>
        </tr>
        <tr>
            <td>firewall-cmd --list-all</td>
            <td>List all</td>
        </tr>
        <tr>
            <td>firewall-cmd --list-all-zones</td>
            <td>Show everything that is configured for every zone</td>
        </tr>
        <tr>
            <td>firewall-cmd --remove-service=http</td>
            <td>Remove http from services / changed runtime configuration</td>
        </tr>
        <tr>
            <td>firewall-cmd --reload</td>
            <td>Reread config file</td>
        </tr>
        <tr>
            <td>firewall-cmd --remove-service=http --permanent</td>
            <td>Remove Service. Take this thing out of your configuration file. Doesn’t change runtime configuration, have to do this separately: </td>
        </tr>
        <tr>
            <td>firewall-cmd --remove-service=http</td>
            <td>Remove http from services / changed runtime configuration</td>
        </tr>
        <tr>
            <td>firewall-cmd --add-service=http --permanent</td>
            <td>Add Service - Changes configuration file</td>
        </tr>
        <tr>
            <td>firewall-cmd --add-service=http</td>
            <td>Add Service - Changes runtime</td>
        </tr>
        <tr>
            <td>To add or remove a service and change runtime</td>
            <td>Run the firewall command with –permanent. Then run reload.</td>
        </tr>
    </table>
</div>