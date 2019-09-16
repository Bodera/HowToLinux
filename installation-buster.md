# Hi there!
I have upgraded from the Debian 9 to Debian 10. Debian Stretch was my first experience on Linux, it was about one year ago. Now I made a step-by-step document where I store procedures and shell commands for upgrade from one distro to another.

This document presents the steps of how do you can install the newest version of the Debian Linux distro. Similiar with Microsoft Windows (haha funny joke), Debian reaches the version 10 named as Buster, the dachshund dog from the Toy Story movie. The Debian 2.1 named as Slink also made tribute to the dachshund toy, but this was in the end of the XX century. 

## Organize your backup
A Seagate tells some insightful info about backup. *Peace of mind? Back it up!*  

* 54% of adults personally have and/or know someone who has lost digital files.
* 27% is the amount of adults who use an external hard drive to back up.
* 72% of the digital assets most valued are multimedia data such as images or videos.
* 35* of the digital assets most valued are work projects or school work.
* 31% of the digital assets most valued are music.

A backup system must offer practicality, security and flexibility. If it is not easy to set up and use, it is unlikely that you will do so. If it does not offer file access and recovery security, it is not truly a backup. In addition, you should have the right options to meet your needs, such as backing up only files that have changed since the last backup.

The key to developing a good backup strategy is directly associated with the availability of data to the organization. Here you must remember the concepts of __RPO__ and __RTO__.  
In order, the first refers to __R__ecovery __P__oint __O__bjective and regards the amount of information that is tolerable to lose, and the second refers to __R__ecovery __T__ime __O__bjective and regards the amount of time it takes operations to return to normal.

The foundation of the backup strategy can be based on three points:  
* Catalog configuration items and their interrelationships.
* Environment requirements survey.
* Backup & Recovery Process Implementation.

Below there are some useful links of how you can implement a backup plan.  

* [Link One](https://www.seagate.com/br/pt/do-more/backing-up-creating-your-back-up-plan-master-dm/): From Seagate (in Portuguese)
* [Link Two](https://www.devmedia.com.br/desenvolvendo-uma-estrategia-eficiente-de-backup-restore-em-ambientes-transacionais/5530): From Sálvio Padlipskas (in Portuguese)
* [Link Three](https://www.controle.net/faq/procedimentos-para-plano-de-backup-corporativo): From Controle Net (in Portuguese)

You must test and validate your backup plan regularly. Avoid troubles as your data, money and effort depends on it. It does :thumbsup:

## Make a bootable USB device
I have good experiences using [UNetbootin](https://unetbootin.github.io/).

You just need to access the [Debian download page](https://www.debian.org/distrib/netinst), pick the image file whose target your system architecture and a download window will prompt at your current session.

So then you need the binary of the UNetbootin, available [here](https://unetbootin.github.io/linux_download.html) for 32 or 64 bit flavors. Download the file and turns it in a properly executable file by typing in the terminal from the same directory where the binary was downloaded:  
```bash
$ chmod +x ./unetbootin-linux64-661.bin
```
Note that the name can vary.

Run the application with:  
```bash
$ ./unetbootin-linux64-661
```

Then format you USB flash drive. I chose NTFS as the file system format. Select where your Debian 10 iso image is, localize your USB device and hit the OK button.

Now you have to discover how to boot from the USB device in your machine BIOS. Generally you just have to enable UEFI boot mode but now that is your pineapple.

## Choose the Graphical Installation Procedure mode
Click and check. Fill and Wait. And read! You have to read before doing any stuff!

The screens that you will see will be far similar to the images contemplated in this [another tutorial.](https://olhardigital.com.br/dicas_e_tutoriais/noticia/quais-sao-as-novidades-do-debian-10-e-como-fazer-a-sua-instalacao/87961)

Not be afraid to ask Google for some technical term you don't know, quite the opposite be proud of yourself!

## Prepare your workspace
At this point I suppose that you could enter at your desktop environment. Here is where the hero journey starts.

__Problem One__

Let's check for some updates! Type it at your terminal:
```bash
$ sudo apt-get update
username is not in the sudoers file. This incident will be reported.
```

Calm down and no panic, drink some water and see how is easy to solve this issue.
```bash
$ whoami
username
$ su
Password> 
# adduser username sudo
# exit
```

This change require a reboot on your system, but I have to make some other changes on my machine that also requires a reboot so don't forget that.

__My USB port seems to not work anymore!__

Uh-oh! Maybe you need to consult a technician, you hardware may leave you high and dry. But that can be a expensive solution and take so much time, you can try a simple trick by editing a particular file. Let's do it.
```bash
# cat /sys/module/usbcore/parameters/autosuspend
2
```

The 2 indicates that autosuspend of USB ports are turned on. Change it in that way:
```bash
# nano /etc/default/grub
```

Set the correspondent line to
```
GRUB_CMDLINE_LINUX_DEFAULT = "quite splash usbcore.autosuspend=-1"
```

Save your alterations. Run `update-grub` as sudo. Reboot is required to changes make effect.


__Qualcomm Atheros Bluetooth Headset just not connect. The Bluetooth just not work!__
Yooooo this one almost drove me to alcoholism! Hahaha just pranking on you.

Debian has a good documentation for Bluetooth issues. The package for solve you problem can vary based on your choose desktop environment. [Take a look at it](https://wiki.debian.org/BluetoothUser).

There they basically tells you to:
1. Install Bluetooth package.
2. Check if Bluetooth service are already running.
2. Install a GUI tool based in your desktop environment.

But I realized what is going on, yeah and I will tell it to you all, not going to keep any secret about this.

#### Edit your sources list
Forgot about that? Because I do. Let's go to the terminal and type:
```bash
# nano /etc/apt/sources.list
```

After each `main` on those lines, add the `contrib` and `non-free` components to your sources list. Save it and update your system with the `apt-get update`.

Now just:
```bash
# apt install firmware-atheros pulseaudio-module-bluetooth
# reboot now
```

Less than 3MB of data downloaded. And if in case you face some unexpected behavior on your Bluetooth adapter, you are able to troubleshoot this incident by shutting down the Bluetooth service and booting it in the sequence.

```bash
$ sudo systemctl status bluetooth #first check for the status
$ sudo systemctl stop bluetooth #so then shut it down
$ sudo systemclt start bluetooth #
```

## Let's add some packages
Here i list the packages/softwares added* to support my work/studies.

1. Redshift
2. Lyx
3. Visual Studio Code
4. Postgres
5. PgAdmin III
6. qBittorrent
7. Docker
8. MongoDB
9. VLC Media Player
10. Neo4J
11. Unity Hub
12. Anaconda
13. Virtual Box
14. Vagrant
15. Git
16. Wireshark
17. Android Studio
18. Insomnia Rest client
19. UNetbootin
20. Kanboard
21. PHP 7
22. Ruby and Ruby On Rails
23. Node.js 12
24. Tor Browser
25. CDEmu
26. Jenkins
27. Oh-my-zhs
28. Awesome WM
29. Chromium
30. Firefox-ESR
32. Eclipse IDE for Java and Rust
33. Remmina

\**(this list can be updated)*

KDE provides a extensive variety of tools. So I just need extra tools for development.

## Bye for now
Now is up to you. Happy study for ya.
