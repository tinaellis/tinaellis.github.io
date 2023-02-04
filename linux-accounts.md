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

### Adding and Removing Accounts
Adding and removing accounts with explanations and argument options.

| Command                       | Description                                                    |
|:------------------------------|:---------------------------------------------------------------|
| useradd accountname           | Create user. Makes a home directory and gives it default shell |
| userdel accountname           | Delete user. Doesn’t fully remove everything, use -r arguments |
| userdel -r accountname        | Deletes the user and associated mailbox/directory stuff        |
| passwd deleteme               | Deletes the password and allows you to create a new one        |

### Unique IDs and Directories

| Command                       | Description                                                                         |
|:------------------------------|:------------------------------------------------------------------------------------|
| useradd -u 1500 username      | u option Specifies a unique user ID (instead of default)                            |
| useradd -g 1501 username      | g option Specifies a unique group ID (instead of default)                           |
| useradd -d /home/user8 u8     | d option Adds the user with a home directory of /user8 instead of the username “u8” |
| useradd -M user9              | M option Doesn’t create a home directory                                            |

<em>*ID numbers 1500, 1501, 1501 have no special meaning</em>

### Shells
The default shell specifies what program or process will be started when the user logs in.

| Command                       | Description                                          |
|:------------------------------|:-----------------------------------------------------|
| useradd -s /bin/tcsh username | s option Sets the shell, here we specified tcsh      |
| useradd -D                    | D option Shows you what it can change                |
| useradd -D -s /bin/tcsh       | D -s Changes the default shell for all new users     |

### Groups
Groups make it easier to control permissions for multiple users.

| Command                          | Description                                                |
|:---------------------------------|:-----------------------------------------------------------|
| id username                      | Display users UserID, GroupID, and what groups they are in |
| groups username                  | Display the group the user is in                           |
| groupadd groupname               | Add a group                                                |
| groupdel groupname               | Remove a group                                             |
| usermod -a -G groupname username | Assign a secondary group to a user                         |
| gpasswd -d username groupname    | Remove a user from a group                                 |

### Finger

| Command                                                             | Description                                            |
|:--------------------------------------------------------------------|:-------------------------------------------------------|
| chfn username                                                       | As root you can change this for a user                 |
| useradd -c “FirstName LastName” username                            | Don't use quotes if you only want to change first name |
| useradd -c “Firstname Lastname,New York,444-4444,555-5555” username | Changing additional fields                             |