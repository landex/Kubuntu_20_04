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
### Install ***GIT***
Run command to install git.
```shell
sudo apt install git -y
```
The version of git installed.
```shell
youruser@kubuntu:~$ git --version
git version 2.25.1
youruser@kubuntu:~$ 
```


### Install ***ZSHELL***

Installing *zshell*, for me is best shell of *Linux*.
```shell
sudo apt install zsh -y
```
To start **zshell** set up, type *zsh* in Konsole, but I prefer manually configuration of **zshell**.

If you type *zsh* this window will be displayed, is only you follow the window information to make changes.

***Type q to quit***



## References
***Instalation*** >>> https://userbase.kde.org/Kubuntu/Installation
***Git*** >>> https://linuxconfig.org/how-to-install-git-on-ubuntu-20-04-lts-focal-fossa-linux
