# ARM Board Setup

## Table of Contents <!-- omit in toc -->

- [ARM Board Setup](#arm-board-setup)
  - [Software / Hardware](#software--hardware)
  - [Install arm-embedded-toolchain](#install-arm-embedded-toolchain)
  - [Install ST Link](#install-st-link)

## Software / Hardware

|                    |                  |
| :----------------- | :--------------- |
| **Development OS** | Ubuntu 18.04     |
| **Board**          | STM32F412G-Disco |
| **Arm Toolchain**  | 7.3.1            |

## Install arm-embedded-toolchain

Remove existing tools
```sh
sudo apt-get remove gcc-arm-none-eabi binutils
```

Add repository and install gcc
```sh
sudo add-apt-repository ppa:team-gcc-arm-embedded/ppa
sudo apt-get update
sudo apt-get install gcc-arm-embedded
```

## Install ST Link
For in-depth instructions, see https://github.com/texane/stlink/blob/master/doc/compiling.md

Must be built from source on Debian.
```sh
# If not already installed, install the following dependencies 
# (devscripts and debhelper only needed for Debian builds)
sudo apt install build-essential cmake libusb-1.0 libusb-1.0-0-dev devscripts debhelper
# Clone github repo
git clone https://github.com/texane/stlink.git
cd stlink
# build
make
# Add executable to path or copy to usr area
sudo cp st-* /usr/local/bin/
```

