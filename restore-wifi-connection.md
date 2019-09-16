# The issue
From time to time, wifi signal downs and couldn't reconnect to it without rebooting.

Also after displug wired connection couldn't reconnect to wifi.

## Solution
List all known connections. The first columns in the output is the _SSID_ and the second is the _UUID_.
```bash
nmcli c
```

Connect to the desired UUID and inform the software to ask for the password.
```bash
nmcli c up uuid <uuid here> --ask
```

### Tested environment
__Distro__ - Debian 10
__Graphical environment__ - KDE Plasma
