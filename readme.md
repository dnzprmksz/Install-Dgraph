# Dgraph Install Scripts

This repository is home to the installation scripts that you find at `https://get.dgraph.io` and others.

Works for:

* :white_check_mark: Ubuntu 16.04 and above 
* :white_check_mark: macOS Sierra and above
* :white_check_mark: Windows 10 and above
* :white_check_mark: Windows Server 2016 above

<!-- Todo: Add Windows Version with Powershell version tested. -->
<!-- Todo: Add Systemd references. -->

# Install Dgraph on Linux and macOS

<!-- Todo: Add Brew formula here. -->

### Using Shell

From `https://get.dgraph.io`

Download latest:
```shell
curl https://get.dgraph.io -sSf | bash
```

Download latest and install as Systemd services (just Linux):

```shell
curl https://get.dgraph.io -sSf | bash -s -- --systemd
```

With Environment Variables:

```shell
curl https://get.dgraph.io -sSf | VERSION=v21.03.0-beta1 bash
```

## Flags

Add `-s --` before the flags.

>`-y | --accept-license`: Automatically agree to the terms of the Dgraph Community License (default: “n”).

>`-s | --systemd`: Automatically create Dgraph’s installation as Systemd services (default: “n”).

>`-v | --version`: Choose Dgraph’s version manually (default: The latest stable release, you can do tag combinations e.g v21.03.0-beta1 or -rc1).


## Environment Variables

>`ACCEPT_LICENSE`: Automatically agree to the terms of the Dgraph Community License (default: “n”).

>`INSTALL_IN_SYSTEMD`: Automatically create Dgraph’s installation as Systemd services (default: “n”).

>`VERSION`: Choose Dgraph’s version manually (default: The latest stable release).

>`DATA_PATH`: Set Dgraph’s data path in Systemd service (default: /var/lib/dgraph).

>`LOG_PATH`: Set Dgraph’s log path in Systemd service (default: /var/log/dgraph).

>`ZERO_FLAGS`: Set additional flags for Zero in Systemd service (default: unset).

>`ALPHA_FLAGS`: Set additional flags for Alpha in Systemd service (default: unset).

>`START_ALPHA`: Start Alpha in Systemd service. Setting this to “n“ will start only Zero service (default: “y“).

# Install Dgraph on Windows

### Using Powershell

This script needs to be executed with ExecutionPolicy set as RemoteSigned"
please run (as Administrator):"

```
Set-ExecutionPolicy -ExecutionPolicy "RemoteSigned"
```

After run the script you can set it to `-ExecutionPolicy "Undefined"`

From `https://get.dgraph.io/windows`

Download latest:

```shell
iwr https://get.dgraph.io/windows -useb | iex
```

With Environment Variables:

```shell
$Version="v21.03.0"; $acceptLicense="yes"; iwr http://get.dgraph.io/windows -useb | iex
```

Download the script and run locally

```shell
iwr http://get.dgraph.io/windows -useb -outf install.ps1; .\install.ps1
```

Run locally with flags

```shell
iwr http://get.dgraph.io/windows -useb -outf install.ps1; .\install.ps1 -version v21.03.0 -acceptLicense yes
```

## Flags

>`-acceptLicense`: Automatically agree to the terms of the Dgraph Community License (default: ask).

>`-version`: Choose Dgraph’s version manually (default: The latest stable release, you can do tag combinations e.g v21.03.0-beta1 or -rc1).

## Environment Variables

>`$Version="v21.03.0"`: Choose Dgraph’s version manually (default: The latest stable release).

>`$acceptLicense="yes"`: Choose Dgraph’s version manually (default: The latest stable release, you can do tag combinations e.g v2.0.0-beta1 or -rc1).

## Compatibility

This Script works on Windows 10, some Windows containers and Windows Server 2016 only.

<!-- Todo: Check Compatibility with Windows Subsystem for Linux. -->
