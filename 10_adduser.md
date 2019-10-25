# ハンズオン用に自分のアカウントを作成する

ハンズオンでは、1台の Jetson Nano を複数人で利用するため、それぞれのユーザーアカウントを作成する。

```
jetson@jetson:~$ sudo adduser ishida
[sudo] password for jetson: (※ jetsonユーザーのパスワードは'jetson')
Adding user `ishida' ...
Adding new group `ishida' (1001) ...
Adding new user `ishida' (1001) with group `ishida' ...
Creating home directory `/home/ishida' ...
Copying files from `/etc/skel' ...
Enter new UNIX password:
Retype new UNIX password:
passwd: password updated successfully
Changing the user information for ishida
Enter the new value, or press ENTER for the default
	Full Name []: Kensuke ISHIDA
	Room Number []:
	Work Phone []:
	Home Phone []:
	Other []:
Is the information correct? [Y/n]
Adding new user `ishida' to extra groups ...
Adding user `ishida' to group `audio' ...
Adding user `ishida' to group `video' ...
Adding user `ishida' to group `gdm' ...
```

作成したユーザーが sudo できるようにする。

```
$ sudo usermod ishida -a -G sudo
```

作成できたら、別のターミナルからSSHでログインできることを確認する。

```
$ ssh ishida@jetson
Welcome to Ubuntu 18.04.3 LTS (GNU/Linux 4.9.140-tegra aarch64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

This system has been minimized by removing packages and content that are
not required on a system that users do not log into.

To restore this content, you can run the 'unminimize' command.

0 packages can be updated.
0 updates are security updates.


The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

ishida@jetson:~$ 
```