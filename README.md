# cpanel-recovery
This is a script, To Reset File and Folder Permissions and Ownership for a user account in Cpanel

Use this script to reset the permissions and ownership of files and folders on a Cpanel user account. This script will iterate through a users Cpanel account files in public_html and set the folder to 0755 and files to 0644.

Why Use This Script?
Sometimes permissions and ownership of folders and files can get conflicted, especially if you are moving accounts to different servers or renaming a Cpanel account. Also, account owners might mistakingly set a folder to 777 which is bad news and unnecessary on a Cpanel server.

NOTE: Before you start you need:

1. Logged in as root user to the WHM server with SSH
2. Know the user name for the account you wish to reset
3. Have already installed the fixperms.sh script at /root/fixperms.sh.

Replace {username} with the username you wish to repair.

`/root/fixperms.sh {username}`
<br>

With the command below you can make a server-wide fix which will iterate through all the users on your server and repair permissions. WARNING: if you have a lot of accounts on the server, this can take a little while.

`for i in ls -A /var/cpanel/users ; do ./root/fixperms.sh $i ; done`
Below is the script to install on WHM server.

Just install it to /root/ on your server and called it fixperms.sh

Thank you to thecpaneladmin.com for this script.
