# R for Windows [![AppVeyor Build Status](https://ci.appveyor.com/api/projects/status/github/kendonb/base)](https://ci.appveyor.com/project/kendonb/base)

> Official repository for building R on Windows

This repository is used for daily builds on [appveyor](https://ci.appveyor.com/project/jeroen/base) which get deployed on the [ftp server](https://ftp.opencpu.org).

## Local Requirements

Building R on Windows requires the following tools:

 - Latest [Rtools](https://cran.r-project.org/bin/windows/Rtools/) compiler toolchain
 - Recent [MiKTeX](https://miktex.org/) + packages `fancyvrb`, `inconsolata`, `epsf`, `mptopdf`, `url`
 - [Inno Setup](http://www.jrsoftware.org/isdl.php) to build the installer
 - Perl such as [Strawberry Perl](http://strawberryperl.com/)

The [appveyor-tools.ps1](scripts/appveyor-tool.ps1) powershell can be used for unattended installation of these tools.

## Building

To build manually first clone this repository plus dependencies:

```
git clone https://github.com/rwinlib/base
cd base
git submodule update --init
```

Running `build-r-devel.bat` or `build-r-patched.bat` will automatically download the latest [R-devel.tar.gz](https://stat.ethz.ch/R/daily/R-devel.tar.gz) or [R-patched.tar.gz](https://stat.ethz.ch/R/daily/R-patched.tar.gz) and start the build.

```
build-r-devel.bat
```

The [appveyor.yml](appveyor.yml) file has more details.

## AppVeyor Deployment

This repository is used for daily builds on [appveyor](https://ci.appveyor.com/project/jeroen/base) which get deployed on the [ftp server](https://ftp.opencpu.org). See [appveyor.md](appveyor.md) and [appveyor.yml](appveyor.yml) for configuration details.
