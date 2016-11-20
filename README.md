# how-to
Enable user=admin ssh access by public key authentication, SELinux
```
chown -R admin:admin /home/admin/.ssh
chmod 700 /home/admin/.ssh;
chmod 600 /home/admin/.ssh/*
restorecon -R -v /home/admin/.ssh
```

