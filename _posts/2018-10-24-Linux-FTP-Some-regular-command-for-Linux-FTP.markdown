---
layout: post
title: "Linux-FTP-Some regular command for Linux FTP"
---
!!!!!! Note: The initial script of vsftp is located on /etc/init.d !!!!!!

1、check ftp service status
command：service vsftpd status
PS：if notice message "vsftpd: command not found"，then change environment variable PATH. 
2、start ftp
command：service vsftpd start
3、check ftp process
command：ps -ef|grep -i ftp
command：netstat -an | grep 21 --??

**normal command after FTP service started**

1、connect to FTP    
command：ftp ip address/hostname
type correct ftp user and password(be defined in file /etc/vsftpd/vsftpd.user_list)

2、check files on ftp host
same as usual Linux command, likd:
ftp> ls 
ftp>pwd

3、更改本地电脑的目录
ftp>lcd
ftp>lcd ..

4、下载文件
ftp> get test.txt
ftp> mget *.txt 
PS：
a)下载到了本地主机的当前目录下。比如，在/opt/ipnet/test下执行ftp，都下载到这个目录了。
b)批量下载每下载一个文件就会有确认提示，可以关闭这个提示，prompt off

 5、上传文件
 ftp> put test1.txt /usr/cc/testAB.htm  
 ftp> mput *.txt
 PS：上传文件都来自于本地主机的当前目录下。比如，在/opt/ipnet/test下运行的ftp命令，则上传的文件都是/opt/ipnet/test目录下的

 6、文件传输类型
 a)查看ftp> type
  Using binary mode to transfer files.

 7、关闭
 ftp> bye
 ftp> quit
