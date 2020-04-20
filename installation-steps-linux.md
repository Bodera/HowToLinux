# Setup development environment on Linux

A short document containing the most updated steps to install the required tools for develop in a Windows OS popular technologies.

## Local environment details

* Debian 10 (buster)
* x86_64 architecture
* intel i5-5200U 2.20GHz
* 8GB RAM

## Procedures for installation

1. [Android Studio v3.6](https://github.com/Bodera/learnPath_Debian/tree/Bodera-debian-dev/installation-steps-linux#android-studio)
2. [Genymotion v3.1](https://github.com/Bodera/learnPath_Debian/tree/Bodera-debian-dev/installation-steps-linux#genymotion)
3. [.NET Core v3.1](https://github.com/Bodera/learnPath_Debian/tree/Bodera-debian-dev/installation-steps-linux#net-core)

### Android Studio

1. Go to the [download page](https://developer.android.com/studio).
2. Extract the file downloaded.
3. Turn the `studio.sh` into a executable file.

```bash
chmod +x ./studio.sh
```

### Genymotion

1. Go to the [download page](https://www.genymotion.com/fun-zone/).
2. Register an account.
3. Install VirtualBox from the [download page](https://www.virtualbox.org/wiki/Linux_Downloads)
4. Install dependencies.

```bash
sudo apt install libqt5opengl5 linux-headers-4.19.0-8-amd64
```

5. Install the package.

```bash
sudo dpkg -i virtualbox-6.1_6.1.6-137129_Debian_buster_amd64.deb
```

6. Turn the `genymotion.run` in a executable file.

```bash
chmod +x ./genymotion.run
```

### .Net Core

1. Add the Microsoft package signing key to the list of trusted keys.
2. Add the repository to the package manager.
3. Install required dependencies.

```bash
wget -O- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/debian/10/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
```

4. Install .NET Core SDK

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-sdk-3.1
```
