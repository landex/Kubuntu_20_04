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
### Install GIT
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


### Install ZSH(ZSHELL)

Installing *zshell*, for me is best shell of *Linux*.
```shell
sudo apt install zsh -y
```
To start **zshell** set up, type *zsh* in Konsole, but I prefer manually configuration of **zshell**.

If you type *zsh* this window will be displayed, is only you follow the window information to make changes.

***Type q to quit***

<img align="center" src="https://github.com/landex/Kubuntu_20_04/blob/master/images/Screenshot_20200930_134831.png" alt="drawing" width="400"/>

Version of ***zsh*** installed.
```shell
youruser@kubuntu:~$ zsh --version
zsh 5.8 (x86_64-ubuntu-linux-gnu)
youruser@kubuntu:~$ 
```

***Atention***
*If you can use the guided configuration, type **ksh** in your terminal due this the configuration window will be displayed.*

### Undestand the ZSHELL files configuration

Access your home directory *cd ~ * To confirm if you stay in your home directory.
```shell
kubuntu% pwd
/home/yourusername
kubuntu% 
```


**.zprofile** - is sourced on all invocations of the shell, unless the -f option is set. It should contain commands to set the command search path, plus other important environment variables run command below to create empty file

```shell
touch .zprofile
```

**.zshrc** - is sourced in interactive shells. It should contain commands to set up aliases, functions, options, key bindings, etc.
```shell
touch .zshrc
```

**.zshenv** - should not contain commands that produce output or assume the shell is attached to a tty. run command below to create empty file
```shell
touch .zshenv
```

**.zhistory** - to save command history.
```shell
touch .zhistory
```

Files created.
```shell
-rw-rw-r--  1 youruser youruser      0 set 30 19:21 .zprofile
-rw-rw-r--  1 youruser youruser      0 set 30 19:21 .zshrc
-rw-rw-r--  1 youruser youruser      0 set 30 19:21 .zshenv
-rw-rw-r--  1 youruser youruser      0 set 30 19:21 .zhistory
```
### My .zshrc
**History of commands**
```shell
kubuntu% echo "# History configuration" >> .zshrc
kubuntu% echo HISTSIZE=1000 >> .zshrc 
kubuntu% echo HISTFILE=~/.zhistory >> .zshrc
kubuntu% echo SAVEHIST=1000 >> .zshrc
kubuntu% 
```
File after this configuration
```shell
kubuntu% more .zshrc 
# History configuration
HISTSIZE=1000
HISTFILE=~/.zhistory
SAVEHIST=1000
kubuntu% 
```
After changes in *.zshrc* you need reload file to Konsole use the new configuration, so run command below.
```shell
kubuntu% source .zshrc 
kubuntu% 
```
To facility this, create the alias below.
```shell
echo "# My aliases" >> .zshrc
echo alias zload="'source ~/.zshrc'" >> .zshrc
```
### Syntax highlighting
To install syntax highlightin run command below.
```shell
sudo apt install zsh-syntax-highlighting -y
```
To enable syntax highlighting.
```shell
echo source /usr/share/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh >> ~/.zshrc
```
### Set up Zshell as default
Run command below, to dicovery the directory of installation of zsh.
```shell
kubuntu% type zsh
zsh is hashed (/usr/bin/zsh)
kubuntu%
```
To set up run command below.
```shell
kubuntu%
sudo usermod -s /usr/bin/zsh $(whoami)
kubuntu%
```
Now reboot your machine, in your terminal run command.
```shell
reboot
```

### Colorful Terminal
Syntax Highlighting


<img align="center" src="https://github.com/landex/Kubuntu_20_04/blob/master/images/Screenshot_20200930_205609.png" alt="drawing" width="150"/>

Now we can add more alias to more colors in terminal.
In your *.zshrc* file add lines below.
```shell
# Alias to added color outputs
alias ls='ls --color=auto'
alias dir='dir --color=auto'
alias vdir='vdir --color=auto'
alias grep='grep --color=auto'
alias fgrep='fgrep --color=auto'
alias egrep='egrep --color=auto'
```
Result.

<img align="center" src="https://github.com/landex/Kubuntu_20_04/blob/master/images/Screenshot_20200930_210140.png" alt="drawing" width="250"/>

### VIM or VI???
I prefer *vim*, for why? For why like... :smiley:
But I use, *vim* only to quick edition of scripts and files, to create scripts and other programs I prefer **VSCode**.
Installing **vim**

```shell
kubuntu% sudo apt install vim -y
```
So after installation, we need create a file in our home called *.vimrc*
```shell
touch .vimrc
```
Add this configurations in *.vimrc* to turn on line number and syntax highlighting.
```shell
echo syntax on >> .vimrc
echo set number >> .vimrc
```

Add an alias to **vim**, to when you type **vi** system call the **vim**.
```shell
echo alias vi='vim' >> .zshrc
```

Testing if work, open a **.zshrc** file and validate that the file is colorful.


<img align="center" src="https://github.com/landex/Kubuntu_20_04/blob/master/images/Screenshot_20200930_212035.png" alt="drawing" width="250"/>


### Configuration of PS1 - Prompt String One

Table of configurations possible to **zshell**

| Sequence  | Printed |
|-----------|---------|
| %T	    | System time (HH:MM)  |
| %*	    | System time (HH:MM:SS) |
| %D	    | System date (YY-MM-DD) |
| %n	    | Current username |
| %B - %b |  Begin - end bold print  |
| %U - %u |  Begin - end underlining |
| %d	    | The current working directory  |
| %~	    | The current working directory, relative to the home directory  |
| %M	    | The computer's hostname  |
| %m	    | The computer's hostname (truncated before the first period)  |
| %l	    | The current tty  |

The Configuration.

```shell
export PS1="[%n@%M] "
```
Output after runned command above
```shell
[youruser@ubuntu]
```
To use this definitely, you added the configuration in your *.zshrc* file.
```shell
echo export PS1="[%n@%M] " >> .zshrc
```

You can added colors in your **zshell**.

Coloar avaiable.
| Name  | Number  |
|-------|---------|
| black | 	0 |
| red 	|1  |
| green |	2 |
| yellow| 3 |
| blue 	|4  |
| magenta| 5|
| cyan 	|6|
| white | 7|

My PS1 zsh.
```shell
PS1=%F{cyan}[%n%f%F{magenta}@%M]%f %F{yellow}[%~]%f 
```

## Java from Oracle
Now we will install Java 11 LTS, I prefer Java from Oracle stead of OpenJDK. To install Java from Oracle follow steps below.

## Ruby 

## VSCode the best editor for me

## References:

***KUBUNTU INSTALLATION*** >>> https://userbase.kde.org/Kubuntu/Installation


***GIT*** >>> https://linuxconfig.org/how-to-install-git-on-ubuntu-20-04-lts-focal-fossa-linux


***ZSH*** >>> https://linuxhint.com/install_zsh_shell_ubuntu_1804/ 


***ZHSELL FILES*** >>> http://zsh.sourceforge.net/Intro/intro_3.html


***COLORS*** >>> https://www.cyberciti.biz/faq/turn-off-color-in-linux-terminal-bash-session/


***VIM*** >>> https://www.linode.com/docs/tools-reference/tools/introduction-to-vim-customization/


***PS1*** >>> https://wiki.gentoo.org/wiki/Zsh/Guide


***COLORS IN PS1*** >>> https://wiki.archlinux.org/index.php/zsh and http://zsh.sourceforge.net/Doc/Release/Prompt-Expansion.html#Prompt-Expansion
