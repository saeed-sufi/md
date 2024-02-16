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
`ps aux | less`
`ps -ax | grep v2ray` // now you know the process id

# To kill a process
`pkill -15 firefox`
`kill -15 <process_id> `or `kill -9 <proccess_id>`

# To see the errors for cron jobs running on your machine, see the postfix output:
`cat /var/mail/saeedsoofi`

* Bash keeps the history in the buffer and doesn't write it to the history log until you log out.

* To repeat the last command: `!!`

* If you want to see what's been added in real time to the end of a file, use `-f` flag with `tail` command: `tail -f output.txt`

* While `ctrl + c` sends the `SIGINT` signal (short for signal intrrupt), `ctrl + d` sends the `SiGQUIT` signal which is a stronger signal.

* These are the ways to quit VIM (first make sure you're in the command mode by hitting escape): 
  
  * `:q` if you haven't made any changes to the file.
  * `:wq` saves the file and quits.
  * `:q!` if you don't want to save changes.
  * `:qa` go to hell VIM.
  
* `less` command is good for reading long files. You can use `\searchterm` to search for sth while in `less`.

* To create multiple folders nested into each other: `mkdir -p my/nested/folder`

* To `tar` the files and folders: `tar -zcf archive.tar.gz file1 folder1` and to `untar` them `tar -xzf archive.tar.gz destination`.

* `&` after a command means run it in the background. For example: `yes > /dev/null &`.

* To see the list of users: `cat /etc/passwd`

* `sudo su` will create a session where you are the superuser. Write `exit` to exit this session.

* To create new user `sudo useradd brian` and set a password for this user: `sudo passwd brian` and then you switch user by `su brian`.

* To give the new user sudo privilages: `sudo usermod -aG sudo brian`. This command will add brian to the sudo group.

* To check the environment variables set in Shell: `printenv`.

* To set new environment variables edit this file: `sudo nano /etc/environment`. Everytime your bash session starts up it's going to read the env variables. The variables defined in this file are available to every user.

* If you want to define `env` variables that are available to your user (not everyone) then define and `export` them in your `~/.bashrc` or `~/.zshrc` file. Every user has his own `~/.bashrc`.

* `ps` shows what you as the user is running and `ps aux` shows what processes all the users are running. 

* You can list the `jobs` running in the background by: `jobs`. Or press `Ctrl + z` to pause a running process. And say `bg 1` to run the process again in the background or `fg 1` to bring the process back to the foreground.

* If a commands returns a zero, it means the process finished succefully. You can check if the returned value is `0` by `echo $?`. Anything other that `0` means the process did not finish successfully. 

* The `&&` operator between commands runs only if the command prior to `&&` returns `0`.

* You can run subcommands inside `$()`. For example, `echo the current date is $(date)`.

