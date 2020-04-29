## Here are some reminders for new users:

1. Backup your data  
2. Secure your password and security keys  
3. KISS (keep it simple stupid)  
4. Don't over-engineer your system  
5. Read your log files  
6. The FIRST error is the one that counts  
7. RTFM (read the fine manual)  
8. Search the Internet before asking questions  
9. Don't be root when you don't have to be  
10. Don't mess with the package management system  
11. Don't type anything you don't understand  
12. Don't change the file permissions (before the full security review)  
13. Don't leave your root shell until you __TEST__ your changes  
15. Always have an alternative boot media (USB memory stick, CD, …)  

## Power up your device

Login using the promtp by hiting `Ctrl`+`Alt`+`F1`
```bash
your_device login: *username*
Password: *not even a dot, its invisible for the user*
username@your_device:~$ 
```

## From master to slave.

By using the command `su` you can change the acquire new user privilleges.
```bash
username@your_device:~$ su
Password:
root@your_device:~# su username
username@your_device:~$
```
