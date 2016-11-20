# how-to
Disable SELinux and Disable FirewallD
```
systemctl disable firewalld.service
sed -i /etc/selinux/config -r -e 's/^SELINUX=.*/SELINUX=disabled/g'
systemctl reboot
```

Enable ssh access user=admin by public key authentication, SELinux
```
chown -R admin:admin /home/admin/.ssh
chmod 700 /home/admin/.ssh;
chmod 600 /home/admin/.ssh/*
restorecon -R -v /home/admin/.ssh
```
Installing ZFSonLinux
```
yum -y update && systemctl reboot   # Update and reboot first, to load any upgraded kernel
yum -y install epel-release
yum localinstall --nogpgcheck http://archive.zfsonlinux.org/epel/zfs-release.el7.noarch.rpm
yum -y install kernel-devel zfs
systemctl reboot```
