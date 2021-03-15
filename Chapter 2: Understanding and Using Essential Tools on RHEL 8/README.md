# Notes 

### section 2.2
### Accessing Linux Systems
### Exam objectives 
- Log in and switch users in multiuser targets
- Access remote systems using SSH
- Configure key-based authentication for SSH
- Securely transfer files between systems

---

list machine ip address 

`ip a s`

change to root user 

`su - root` | `su -` | `sudo -i` | `sudo su - root`

using sudo with a non-interactive shell 

`sudo dnf update`

generate ssh keys

`ssh-keygen`

copy ssh key to another server 

`ssh-copy-id user@hostname`

identify the hostname of a machine 

`hostname` 

if you don't want an interactive shell and only want to return information about the system 

`ssh user@hostname cat /etc/redhat-release`

copy files from another server 

`scp user@hostname:/home/user/file.txt .`

use secure ftp - sftp

`sftp user@hostname` opens an interactive session 

copy files via sftp 

`mget *.txt` copy all .txt files in current directory 

---

### section 2.3
### Using System Documentation on RHEL 8
### Exam objectives
- Locate, read, and use system documentation including man, info, and files in /usr/share/doc
---

<b>man pages</b>: traditional unix documentation format w/ vim key bindings

<b>info docs</b>: default doc format for GNU w/ emacs key bindings

<b>`/user/share/docs`</b>: system documentation, various file formats, e.g., txt, md, html, css, png, etc...

installing apache 

check if there is any documentation on the system 

`man httpd` 

`info https`

`ls -la /usr/share/doc | egrep -i "httpd|mariadb|mysql"`

using the help flag 

`mariadb --help`

paginate by piping through `more` | `less`

`mariadb -?` 

> note: while searching man pages use `/` to search page

> while searching man, use `h` for help and `q` fto quit

for extra help you can use the `whatis` command

`whatis https` 

> output: `httpd (8)            - Apache Hypertext Transfer Protocol Server`

you can list multiple packages 

`apropos httpd` 

lists more information 

>output: 

`httpd (8)            - Apache Hypertext Transfer Protocol Server`
`httpd.service (8)    - httpd unit files for systemd` 
`httpd.conf (5)       - Configuration files for httpd`
`httpd.socket (8)     - httpd unit files for systemd`
`httpd@.service (8)   - httpd unit files for systemd`
`ostree-trivial-httpd (1) - Simple webserver`

lookup specific information 

`man 8 httpd.socket` 

`info httpd` 

`ls -al /usr/share/doc | egrep -i "httpd|mariadb|mysql"`

> output: lists directories containing information files  

`drwxr-xr-x.   2 root root  4096 Mar 15 03:22 httpd`

`drwxr-xr-x.   2 root root    35 Mar 15 03:22 httpd-tools`

`drwxr-xr-x.   2 root root     6 Dec  3 11:46 mariadb`

`drwxr-xr-x.   2 root root    20 Mar 15 03:22 mariadb-connector-c`

