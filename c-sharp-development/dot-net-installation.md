# Installing .NET Core on Debian

The information provided on this document is available at the [MS docs page](https://docs.microsoft.com/en-us/dotnet/core/install/linux-debian#debian-10-).

First of all, add the MS package signing key tothe list of trusted keys and then add the package repository. __Sudo__ privileges are necessary.

```bash
wget https://packages.microsoft.com/config/debian/10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
dpkg -i packages-microsoft-prod.deb
```

Now a depency package is needed to be installed: `apt-transport-https` a transitional package for https support on *apt flavor* Linux distros.

```bash
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https
```

Proceed the installation of the software development toolkit (SDK) for .NET Core. By installing .NET Core SDK, you don't need to install the corresponding runtime.

```bash
sudo apt-get update; \
  sudo apt-get install -y dotnet-sdk-3.1
```

The commands below install the ASP .NET Core Runtime, which is the most compatible runtime for .NET Core.

```bash
sudo apt-get update; \
  sudo apt-get install -y aspnetcore-runtime-3.1
```

Issues regarding to *Unable to locate package d{netcore-package}*, are dealt at the [APT troubleshooting MS documentation](https://docs.microsoft.com/en-us/dotnet/core/install/linux-debian#unable-to-locate).
