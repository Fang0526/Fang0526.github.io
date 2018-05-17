---
layout: post
title:  "A probably solution for FTP error 'vsftpd failed - problably invalid config.'"
---
When I trying to config vsftpd on Ubuntu i met two problems by now, here is the details：
1. change /etc/vsftp.conf to make local_root = /home/{user}/myftp and remove the old root /var/myftp, but when connecting to ftp,
   after typing ftp username and password, error message 'cannot change direction: /var/myftp' kept showing
   This problem has not been fixed, will try later
2. after making sure local_root to default value /var/myftp and this folder exists, start vsftpd service(Command: service vsftpd start),
  error message 'vsftpd failed - probably invalid config.' kept showing, following is troubleshooting steps:
  a. add message to /etc/init.d/vsftpd to check where the error happens
  b. it shows 'if ! ps -C vsftpd | grep -qs "${_PID}"' returns 0 which should be 1(means vsftpd has been started, 
      PID be loged on file /var/run/vsftpd/vsftpd.pid after /usr/sbin/vsftpd be executed)
  c. i tried to change command line 'listen_ipv6=YES' to 'listen_ipv6=NO', it works!!!

i have not quite understand the reason of this issue and this solution, so mark it down here. Hopes will find the answer later on.
