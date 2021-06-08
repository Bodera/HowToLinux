# Grub rescue

Hi, a few days ago fate messed up my Windows update, as result GRUB on my machine got corrupted.

After some research I realized that everything can be fixed by the terminal, so I compiled the resolution steps in this document.

## About the disease

![Error image](https://3.bp.blogspot.com/-R8ggqY7IRxc/WmITpP3xQNI/AAAAAAAAABM/YHEIto1xWoU9ojjTgiRSKae7z-yQzj61ACLcBGAs/w1200-h630-p-k-no-nu/gruberror.jpg)

From this screen we will start the work, type `ls` in order to list available partitions.

```bash
> ls
```

From the alternatives presented, type `ls + partition name` until bash echoes:

> (somepartition): Filesystem is ext2

This indicates that the partition contains a Linux kernel, where GRUB is.

```bash
> set boot=(hd0,msdos?)
> set prefix=(hd0,msdos?)/boot/grub
> insmod normal
> normal
```

No one of commands above produces output unless you type something wrong.

_where ? represents the partition number_

## About the diagnosis

The system should automatically reboot and display the boot screen where you can choose to which OS login.

But we've just done a temporary fix, under the covers GRUB remains corrupted.

So back to terminal, and updtade grub files.

```bash
> sudo update-grub
```

This command prints the current OS images found in the hard drive, and also generates necessary grub files.

```bash
> sudo apt-get purge $( dpkg --list | grep -P -o "linux-image-\d\S+" | grep -v $(uname -r | grep -P -o ".+\d") )
```

This one line hack purges automatically old kernel versions that remained on disk.

```bash
> sudo grub-install /dev/sda
```

This was the last command needed, it restores original grub configuration to the rigth partition.
