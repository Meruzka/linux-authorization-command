# linux-authorization-command
A collection of Linux commands and configurations for managing system authorization, including users, groups, permissions, and sudo access.


users/user-management.md
# Some basics but useful configurations

```bash
sudo adduser username

# To delete a user
sudo userdel username

# To change a user's password
sudo passwd username

# Lock / Unlock a User
sudo usermod -L username   # Lock
sudo usermod -U username   # Unlock

# View User Info
id username


---

#### 👥 `groups/group-management.md`

```markdown
# Group Management

## Create a Group

```bash
sudo groupadd groupname

## Add User to a Group
sudo usermod -aG groupname username

# View Group Info
groups username

# Remove User from Group
sudo gpasswd -d username groupname


---

#### permissions/file-permissions.md

```markdown
# File Permissions
## View File Permissions

```bash
ls -l

## Change Ownership
sudo chown user:group filename

## Change Permissions, it will depends of the write or read permissions
chmod u+x script.sh  # Add execute to user
chmod 755 filename   # rwxr-xr-x

## Recursive Permission Change
chmod -R 755 /path/to/directory

#### some sudo/sudo-configuration.md`

```markdown
# Sudo configuration

## add user to sudoers

```bash
sudo usermod -aG sudo username

## Edit Sudoers File (safe way)
sudo visudo

## grant all access to a user
username ALL=(ALL:ALL) ALL

## allow running specific commands only
username ALL=(ALL) NOPASSWD: /path/to/command
