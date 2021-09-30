
## Lab 2 : CEG 3400

### Authentication and Permissions

#### Name: Jiaran Liu

Names of teammates:
* GrantTreadway
* G Loranger

---

### Task 1 - Users

* Type your simple password here:

  1word
 
* Upload your `id_rsa.pub` to this repo
* Encrypt your password with matthew.kijowski@wright.edu as the `--recipient` and upload it to `password.gpg`
* paste the relevant lines in `/etc/passwd` and `/etc/group` below that show you created your user
  ```
  etc/passwd:
    grant:x:1001:1001:,,,:/home/grant:/bin/bash
    loranger:x:1002:1002:,,,:/home/loranger:/bin/bash
    jiaran:x:1003:1003:,,,:/home/jiaran:/bin/bash

  etc/group:
    grant:x:1001:
    loranger:x:1002:
    jiaran:x:1003:

  ```

---

### Task 2 - Permissions

* What were the permissions on each of the users' home directories?
  ```
  ls -lah /home
    total 24K
    drwxr-xr-x  6 root     root     4.0K Sep 23 03:01 .
    drwxr-xr-x 23 root     root     4.0K Sep 23 00:48 ..
    drwxr-xr-x  2 grant    grant    4.0K Sep 23 02:47 grant
    drwxr-xr-x  2 jiaran   jiaran   4.0K Sep 23 03:01 jiaran
    drwxr-xr-x  2 loranger loranger 4.0K Sep 23 02:54 loranger
    drwxr-xr-x 11 ubuntu   ubuntu   4.0K Sep 23 03:21 ubuntu

  ```
* What command did you use to change the permissions?
  ```
  sudo chmod 770 jiaran
  sudo chmod 770 grant
  sudo chmod 770 loranger

  ```
* What are the permissions on `/etc/shadow`?
  ```
  ls -lh /etc/shadow
    -rw-r----- 1 root shadow 1.3K Sep 23 03:02 /etc/shadow
  ```
* Why does `/etc/shadow` have the permissions that it does?

  Because it's a root file that store the passwd info about users. So only user can read and write. Group can read only. Others don't have any access permission.

* How did you accomplish this task?  IF you updated any of the files above
  (`/etc/passwd` or `/etc/group`) paste the relevant lines here.  
  ```
   ls -lah /home
total 24K
drwxr-xr-x  6 root     root     4.0K Sep 23 03:01 .
drwxr-xr-x 23 root     root     4.0K Sep 23 00:48 ..
drwxrwx---  2 grant    grant    4.0K Sep 23 02:47 grant
drwxrwx---  2 jiaran   jiaran   4.0K Sep 23 03:01 jiaran
drwxrwx---  2 loranger loranger 4.0K Sep 23 02:54 loranger
drwxr-xr-x 12 ubuntu   ubuntu   4.0K Sep 30 22:49 ubuntu
   
   cat /etc/group
sudo:x:27:ubuntu,grant,jiaran,loranger

I accomplish this task by adding the users to the sudo group. 
sudo usermod -aG sudo jiaran
sudo usermod -aG sudo grant
sudo usermod -aG sudo loranger
As the output of cat /etc/group. They are all sudoers, so they can access other users' files.
  ```
  Be thorough in your response, explain how given the above output and 
  a listing of commands run I can know for certain that your user can 
  access other users' files.

---

### Task 3 - SetUID

* Make sure your uncompiled and compiled code is in `/code`
* What were the final permissions on your executable?
  ```
  ```
* What command did you use to setUID?
  ```
  ```
* Copy paste each verification you did for the setuid on your teammates'
  systems into different code blocks below.
  ```
  teammate 1
  ```
  ```
  teammate 2
  ```

---

### Task 4 - Hashcat

* How many passwords did you crack?
* Upload the cracked passwords to this repo `hashcat.output`
* How would you go about cracking ***ALL*** of the passwords?

* Analyze the results of `hashcat.output`, the input wordlists, 
  and the input `shadowfile`.  Were there any duplicate passwords?
  Did they have the same hashes in the shadowfile?  Was one wordlist more
  effective than the others?

