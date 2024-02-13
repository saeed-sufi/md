# To remove an app from ubuntu:
sudo apt-get purge cudatext

# To install a .deb package in ubuntu:
sudo dpkg -i <package path>

# netstat command
To see the processes that are listening for connections;
`sudo netstat -tulpen`

# To see all of the current network connections:
`sudo netstat -atupen`

# To only view the ESTABLISHED connections:
`sudo netstat -atupen | grep ESTABLISHED`

# To create a symlink in the second folder to the first one:
`sudo ln -s /opt/lampp/htdocs/ /home/saeedsoofi`

# To find files in ubuntu:
`sudo find / -name php.ini`

# To change the owenership of a directory from `root` to yourself:
`sudo chown –R saeedsoofi:saeedsoofi ~/myfolder`

# To show network config
`sudo lshw -class network`

# To show ip route
`ip route show`

# To see the list of repositories Ubuntu uses for updates:
`cd /etc/apt/sources.list.d && ls`
`sudo nano /etc/apt/sources.list`


# To list all the GPG keys added to your system:
`sudo apt-key list`
`/etc/apt/sources.list.d/
`/etc/apt/trusted.gpg.d

# To list the running processes:
ps aux | less
ps -ax | grep v2ray // now you know the process id

# To kill a process
pkill -15 firefox
kill -15 <process_id> or kill -9 <proccess_id>

# To see the errors for cron jobs running on your machine, see the postfix output:
cat /var/mail/saeedsoofi


