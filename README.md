# learnPath_Debian
This repository stores guidance about how to professional administrate a Linux environment running Debian as operation system.  
 
 ___
## Purpose
The main purpose for the creation of this repository is to stores a collection of useful tips, patterns and commands instructions when dealing with Debian on Linux (desktops and servers). Therefore this informations intents to improve my competence as IT professional, and hopefully guide new people interested in learning more about correlated technology.  

 ___
## It is only this?
The branch `master` is updated weekly, the branch `Bodera-debian-dev` is updated every 2-4 days instead.  
 
 ___
#### Where do I find `Bodera-debian-dev`?
You can easily go to the `dev` branch by clicking [here](https://github.com/Bodera/learnPath_Debian/tree/Bodera-debian-dev).  
 
 ___
## Environment details
My terminal produces the following output when I run the `uname -a` command.  
```
Linux Unbootable 4.9.0-8-amd64 #1 SMP Debian 4.9.130-2 (2018-10-27) x86_64 GNU/Linux  
```
* Where `Linux` is your kernel name, not BSD, not macOS.  
* `Unbootable` is the hostname, my device frindly name.  
* `4.9.0-8-amd64` is my Linux kernel version. Deeply the first digit `4` explicits the kernel version, the second one `9` tells me the major revision, while the third one `0` tells me the minor revision, the fourth digit `8` indicates the bug fix, and the string `amd64` stands for the distribution.  
* `#1 SMP Debian 4.9.130-2 (2018-10-27)` the debian maintainers have compiled the kernel `1` time. Followed by the timestamp.  
* `x86_64` its my machine hardware architecture.
* `GNU/Linux` its my operating system.

 ___
#### Checking detais about the Linux distribution in your machine: 
My terminal produces the following output when I run the `lsb_release -a` command.  
```
No LSB modules are available.
Distributor ID: Debian
Description:    Debian GNU/Linux 9.6 (stretch)
Release:        9.6
Codename:       stretch
```
 ___
## How do I write a good README?
 Without practice there is no success. Access [here](https://github.com/Bodera/goodPractices_Github), a repository of good practices in GitHub, there are available orientations and hyperlinks references about how to contribute with the community.

 ___
## Contributions
 Pull requests are welcome, but I ask for open an issue for we better discuss about what do you like to change.

## License
 The softwares stored in this repository aren't covered by any license yet.
