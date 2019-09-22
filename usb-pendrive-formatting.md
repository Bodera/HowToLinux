# Formatting USB Drive using the Command Line

1. List all of your devices and identify USB Drive.

```bash
$ df -h
```

2. Umount your pendrive.

```bash
$ sudo umount /dev/sdb1
```

3. Format that little disk.

```bash
$ sudo mkfs.exfat /dev/sdb1
```

These value can change according to the circunstances. Help can be found [here](https://tecadmin.net/format-usb-in-linux/).
