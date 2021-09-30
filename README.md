Task1:
1.simple password: 1word
4.etc/passwd:
  grant:x:1001:1001:,,,:/home/grant:/bin/bash
loranger:x:1002:1002:,,,:/home/loranger:/bin/bash
jiaran:x:1003:1003:,,,:/home/jiaran:/bin/bash

  etc/group:
  grant:x:1001:
loranger:x:1002:
jiaran:x:1003:

Task2:
1.ls -lah /home
  total 24K
drwxr-xr-x  6 root     root     4.0K Sep 23 03:01 .
drwxr-xr-x 23 root     root     4.0K Sep 23 00:48 ..
drwxr-xr-x  2 grant    grant    4.0K Sep 23 02:47 grant
drwxr-xr-x  2 jiaran   jiaran   4.0K Sep 23 03:01 jiaran
drwxr-xr-x  2 loranger loranger 4.0K Sep 23 02:54 loranger
drwxr-xr-x 11 ubuntu   ubuntu   4.0K Sep 23 03:21 ubuntu

2.sudo chmod 770 jiaran
  sudo chmod 770 grant
  sudo chmod 770 loranger
3.ls -lh /etc/shadow
-rw-r----- 1 root shadow 1.3K Sep 23 03:02 /etc/shadow
4.Because it's a root file that store the passwd info about users. So only user can read and write. Group can read only. Others don't have any access permission.
5.sudo usermod -aG sudo jiaran
  sudo usermod -aG sudo grant
  sudo usermod -aG sudo loranger
I accomplish this task by adding users to the sudo group
ls -lah /home
total 24K
drwxr-xr-x  6 root     root     4.0K Sep 23 03:01 .
drwxr-xr-x 23 root     root     4.0K Sep 23 00:48 ..
drwxrwx---  2 grant    grant    4.0K Sep 23 02:47 grant
drwxrwx---  2 jiaran   jiaran   4.0K Sep 23 03:01 jiaran
drwxrwx---  2 loranger loranger 4.0K Sep 23 02:54 loranger
drwxr-xr-x 11 ubuntu   ubuntu   4.0K Sep 23 03:21 ubuntu

cat /etc/group
sudo:x:27:ubuntu,grant,jiaran,loranger
A user can access other users file as a sudoer. So I added them to the sudo group. Instead of sudo adduser. I used sudo usermod -ag sudo <username> to add an exiting user to the sudo group

Task3:

