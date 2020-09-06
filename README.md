common tasks, commands on centos8
1. common linux admin cmds on centos8
2. install, configure Apache HTTPD web server
3. install, configure Nginx web server and proxy
4. install packages, EPEL repo using dnf / yum
5. install Podman, Buildah, Skopeo Containers; Pull an Image; Run a Container
6. install, configure VNC server
7. systemd systemctl for managing services
8. cron to run tasks automatically
9. configure date, time 
10. Kernel modules configuration

1. common linux admin tasks, cmds
$ hostname - returns value stored in /etc/hostname : centos8.ondhia

$ cat /etc/centos-release 
CentOS Linux release 8.2.2004 (Core) 

$ cat /etc/centos-release : returns multi-line infor with NAME, ID, VERSION_ID, etc

kdump - in event of system crash, captures info that helps determine causes;
enabled by default 

dnf update
dnf autoremove
dnf clean all 
rm -rf /var/cache/dnf/

[root@centos8 dnf]# localectl
   System Locale: LANG=en_US.UTF-8
       VC Keymap: us
      X11 Layout: n/a

localectl set-locale  # get-locale

timedatectl   -- gives cur time zone configured
timedatectl list-timezones | grep Los
timedatectl set-timezone America/Los_Angeles

systemctl - to enable, start, stop services

firewall-cmd --get-services | list ports
firewall-cmd --permanent --zone=public --add-service=http
firewall-cmd --permanent --zone=public --add-port=3890/tcp

systemctl get-default
multi-user.target
systemctl set-default graphical.target
systemctl isolate graphical.target

systemctl poweroff | reboot

cat /etc/resolv.conf
nameserver 127.0.0.1
nameserver 10.0.0.8
nameserver 10.0.0.4

Yum provided in CentOS 8 is: Dandified Yum - DNF
It's a symbolic link to dnf

yum repolist
repo id                                        repo name
AppStream                                      CentOS-8 - AppStream
BaseOS                                         CentOS-8 - Base
epel                                           Extra Packages for Enterprise Linux 8 - x86_64
epel-modular                                   Extra Packages for Enterprise Linux Modular 8 - x86_64
extras                                         CentOS-8 - Extras




