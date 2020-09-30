# Hello!!! Let's start!

In this steps by steps, I'll show my configuration to use Kubuntu 20.04 in a MacBook Pro Late 2013, I5 , 128GB SSD and 4 GB of RAM.

### Update the system.

After installation, open Konsole(Is Terminal name in KDE), and run command below.
```shell
sudo apt update
```
The output below indicate that have packages to update.
```shell
[sudo] password for landileite: 
Hit:1 http://br.archive.ubuntu.com/ubuntu focal InRelease
Hit:2 http://br.archive.ubuntu.com/ubuntu focal-updates InRelease
Hit:3 http://br.archive.ubuntu.com/ubuntu focal-backports InRelease
Hit:4 http://security.ubuntu.com/ubuntu focal-security InRelease
Reading package lists... Done
Building dependency tree       
Reading state information... Done
138 packages can be upgraded. Run 'apt list --upgradable' to see them.
```
Now run command to perform upgrade.
```shell
sudo apt upgrade -y
```

## References
***Instalation*** -> https://userbase.kde.org/Kubuntu/Installation
