## Account Basics
<a href="linux">Back</a>

<div class="intro">
    <h3>Account Settings</h3>
</div>

<div class="steps">
    <p>Account settings and details are stored in some of the following directories and files.</p>
    <ul>
        <li>/etc/login.defs - Site-specific configuration for the shadow password suite, <a href="https://man7.org/linux/man-pages/man5/login.defs.5.html" target="_blank">configuration options</a></li>
        <li>/etc/passwd - Main file system used to track user accounts</li>
        <li>/etc/default/useradd - The useradd program uses a collection of default values kept in this file</li>
        <li>/etc/shadow - Location of (user) hashed passwords</li>
        <li>/etc/group - Group information</li>
        <li>/etc/gshadow - Location of (group) hashed passwords</li>
    </ul>
    <p><em>The useradd command modifies the passwd, shadow, group, and gshadow files</em></p>
    <p>Every user will belong to a single primary group, which is listed in the passwd file. A user can also belong to multiple secondary groups.</p>
</div>

<div class="intro">
    <h3>Adding and Removing Accounts</h3>
</div>
<div class="steps">
    <p>Adding and removing accounts with explanations and argument options.</p>
    <table>
        <tr>
            <th>Command</th>
            <th>Description</th>
        </tr>
        <tr>
            <td>useradd accountname</td>
            <td>Create user. Makes a home directory and gives it default shell</td>
        </tr>
        <tr>
            <td>userdel accountname</td>
            <td>Delete user. Doesn’t fully remove everything, use -r arguments</td>
        </tr>
        <tr>
            <td>userdel -r accountname</td>
            <td>Deletes the user and associated mailbox/directory stuff</td>
        </tr>
        <tr>
            <td>passwd deleteme</td>
            <td>Deletes the password and allows you to create a new one</td>
        </tr>
    </table>
</div>

<div class="intro">
    <h3>Unique IDs and Directories</h3>
</div>
<div class="steps">
    <table>
        <tr>
            <th>Command</th>
            <th>Description</th>
        </tr>
        <tr>
            <td>useradd -u 1500 username</td>
            <td>u option Specifies a unique user ID (instead of default)</td>
        </tr>
        <tr>
            <td>useradd -g 1501 username</td>
            <td>g option Specifies a unique group ID (instead of default)</td>
        </tr>
        <tr>
            <td>useradd -d /home/user8 u8</td>
            <td>d option Adds the user with a home directory of /user8 instead of the username “u8”</td>
        </tr>
        <tr>
            <td>useradd -M user9</td>
            <td>M option Doesn’t create a home directory</td>
        </tr>
    </table>
    <em>*ID numbers 1500, 1501, 1501 have no special meaning</em>
</div>

<div class="intro">
    <h3>Unique IDs and Directories</h3>
</div>
<div class="steps">
    <p>Adding and removing accounts with explanations and argument options.</p>
    <table>
        <tr>
            <th>Command</th>
            <th>Description</th>
        </tr>
        <tr>
            <td>useradd -u 1500 username</td>
            <td>u option Specifies a unique user ID (instead of default)</td>
        </tr>
        <tr>
            <td>useradd -g 1501 username</td>
            <td>g option Specifies a unique group ID (instead of default)</td>
        </tr>
        <tr>
            <td>useradd -d /home/user8 u8</td>
            <td>d option Adds the user with a home directory of /user8 instead of the username “u8”</td>
        </tr>
        <tr>
            <td>useradd -M user9</td>
            <td>M option Doesn’t create a home directory</td>
        </tr>
    </table>
    <em>*ID numbers 1500, 1501, 1501 have no special meaning</em>
</div>

<div class="intro">
    <h3>Shells</h3>
</div>
<div class="steps">
    <p>The default shell specifies what program or process will be started when the user logs in.</p>
    <table>
        <tr>
            <th>Command</th>
            <th>Description</th>
        </tr>
        <tr>
            <td>useradd -s /bin/tcsh username</td>
            <td>s option Sets the shell, here we specified tcsh</td>
        </tr>
        <tr>
            <td>useradd -D</td>
            <td>D option Shows you what it can change</td>
        </tr>
        <tr>
            <td>useradd -D -s /bin/tcsh</td>
            <td>D -s Changes the default shell for all new users</td>
        </tr>
    </table>
</div>

<div class="intro">
    <h3>Groups</h3>
</div>
<div class="steps">
    <p>Groups make it easier to control permissions for multiple users.</p>
    <table>
        <tr>
            <th>Command</th>
            <th>Description</th>
        </tr>
        <tr>
            <td>id username</td>
            <td>Display users UserID, GroupID, and what groups they are in</td>
        </tr>
        <tr>
            <td>groups username</td>
            <td>Display the group the user is in</td>
        </tr>
        <tr>
            <td>groupadd groupname</td>
            <td>Add a group</td>
        </tr>
        <tr>
            <td>groupdel groupname</td>
            <td>Remove a group</td>
        </tr>
        <tr>
            <td>usermod -a -G groupname username</td>
            <td>Assign a secondary group to a user</td>
        </tr>
        <tr>
            <td>gpasswd -d username groupname</td>
            <td>Remove a user from a group</td>
        </tr>
    </table>
</div>

<div class="intro">
    <h3>Finger</h3>
</div>
<div class="steps">
    <p>The default shell specifies what program or process will be started when the user logs in.</p>
    <table>
        <tr>
            <th>Command</th>
            <th>Description</th>
        </tr>
        <tr>
            <td>chfn username</td>
            <td>As root you can change this for a user</td>
        </tr>
        <tr>
            <td>useradd -c “FirstName LastName” username</td>
            <td>Don't use quotes if you only want to change first name</td>
        </tr>
        <tr>
            <td>useradd -c “Firstname Lastname,New York,444-4444,555-5555” username</td>
            <td>Changing additional fields</td>
        </tr>
    </table>
</div>