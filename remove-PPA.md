## The simplest is the best
```bash
sudo add-apt-repository --remove ppa:whatever/ppa
```

## Second option
You can achieve the same result by typing:

```bash
sudo apt-get install ppa-purge
```

```bash
sudo ppa-purge ppa:whatever/ppa
```

Note that this will uninstall packages provided by the PPA, but not those provided by the official repositories. If you want to remove them, you should tell it to apt:

```bash
sudo apt-get purge <package_name>
```

Now simple check if it was remove by typing:  
```bash
sudo apt-get update
```

## Da font
Gotcha from [here](https://askubuntu.com/questions/307/how-can-ppas-be-removed).