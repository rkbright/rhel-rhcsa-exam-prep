 # Notes 

### section 2.2

list machine ip address 

`ip a s`

change to root user 

`su - root` | `su -` | `sudo -i` | `sudo su - root`

using sudo with a non-interactive shell 

`sudo dnf update`

generate ssh keys

`ssh-keygen`

copy ssh key to another server 

`ssh-copy-id user@hostname

identify the hostname of a machine 

`hostname` 

rif you don't want an interactive shell and only want to return information about the system 

`ssh user@hostname cat /etc/redhat-release`

copy files from another server 

`scp user@hostname:/home/user/file.txt .`

use secure ftp - sftp

`sftp user@hostname` opens an interactive session 

copy files via sftp 

`mget *.txt` copy all .txt files in current directory 

