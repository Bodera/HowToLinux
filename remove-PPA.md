sudo add-apt-repository --remove ppa:whatever/ppa

sudo apt-get install ppa-purge


sudo ppa-purge ppa:whatever/ppa

Note that this will uninstall packages provided by the PPA, but not those provided by the official repositories. If you want to remove them, you should tell it to apt:

sudo apt-get purge package_name

Gotcha from here: https://askubuntu.com/questions/307/how-can-ppas-be-removed
