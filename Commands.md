systemctl get-default - shows runlevel target that's currently active

locale(/usr/share/i18n/locales) or localectl - Shows geographic location

pwd - present work directory

env - entire current list  (env | less) q - quit less

- timedatectl  #display your current zone settings 
- timedatectl list-timezones | grep -i america
- timedatectl set-timezone America/Los_Angeles

Installing Apache 
- sudo apt update #Update your local package index
- sudo apt install apache2 #Install the apache2 package
- sudo ufw app list #Check the available ufw application profiles
- sudo ufw allow 'Apache'
- sudo ufw status
- sudo systemctl status apache2  #Check with the systemd init system to make sure the service is running 
- curl 127.0.0.1 #validate website is working
                  
                 
Network
  - ip route show
  - sudo dhclient
  - ifconfig = ip addr
  - route
  - netstat -i
  - netstat - l
  - ss -i

Monitoring
  - top 
  - free -h
  - df -ht ext4
  - ps aux | grep sshd
  - journalctl --since "10 minutes ago"
  - cat syslog | grep *
  - less /proc/meminfo - show mem info
- less /proc/cpuinfo - show cpu info
- q - to quit less
- apt update
- ip addr
- iftop -i eth0
- ps aux |grep sshd
- journalctl --since "10 minutes ago"
- cd /var/log
- cat /var/log/syslog |grep sshd
- systemctl status apache2
- systemctl disable apache2
- systemctl enable apache2
- systemctl start apache2
- kill 1127
- killall yes
- nice -19
- renice -15 process

# Users and Groups

- less /etc/shadow
- less /etc/passwd
- less /etc/group
- id username
- who
- w
- last |less

- useradd -m jane
- passwd jane
- cd /etc/skel

- mkdir /var/secret
- groupadd secret-group
- chown :secret-group /var/secret
- usermod -a -G secre-group jane
- chmod g+w /var/secret


# Security

- cd /var/secret

- ls
- su jane
- touch data.txt
- ls -l
- ls -dl
- chmod o+x data.txt

- Read r 4
- Write w 2
- Execute x 1
- Full permissions: 7
- Read/execute: 5
- Execute: 1

- chmod 777 data.txt

- ls-dl
- chmod +s /var/secret
- ls dl


# Hardening Server

- sudo apt update
- sudo apt upgrade
- yum update

- nmap -v -sT localhost
