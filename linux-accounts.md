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
        <li>/etc/shadow/ - Location of (user) hashed passwords</li>
        <li>/etc/group/ - Group information</li>
        <li>/etc/gshadow/ - Location of (group) hashed passwords</li>
    </ul>
    <p><em>The useradd command modifies the passwd, shadow, group, and gshadow files</em></p>
</div>

### Adding and Removing
Account settings and details are stored in some of the following directories and files.

```linux
useradd accountname # Create user. Makes a home directory and gives it default shell
userdel accountname # Delete user. Doesn’t fully remove everything, use -r arguments
userdel -r accountname # Deletes the user and associated mailbox/directory stuff
passwd deleteme # Deletes the password and allows you to create a new one
```

### User and Group IDs
| Command      | Description |
| :---        |    ----:   |
| useradd -u 1500 username     | u option specifies a unique user ID (instead of default)      |
| useradd -g 1501 username   | g option specifies a unique group ID (instead of default)       |