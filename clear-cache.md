## Commands for clear cache memory (a.k.a RAM) in Linux distributions


__Note:__ You must be logged as `sudo` to perform the commands given bellow.

1. For PageCache
```bash
> sync; echo 1 > /proc/sys/vm/drop_caches
```

2. For dentries and inodes
```bash
> sync; echo 2 > /proc/sys/vm/drop_caches
```

3. For PageCache, dentries and inodes
```bash
> sync; echo 3 > /proc/sys/vm/drop_caches
```
