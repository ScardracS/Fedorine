# <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/3/3f/Fedora_logo.svg/200px-Fedora_logo.svg.png" width="25" height="25"> PinePhone Fedora Setup

A collection of scripts to sets up Fedora and run off your PinePhone SD card. Soon to be part of the Fedora Mobility SIG.

Original scripts files are provided by https://github.com/nikhiljha/pp-fedora-sdsetup. I wouldn't have done nothing of that without them.

These scripts are modified from the original one: this won't install kernel from njha/mobile but the version provided directly by megi. 

## **🚨🚨🚨 WARNING! 🚨🚨🚨**
This is a **barely tested** collection of scripts written by someone who has never written a bash script for other people to use! It involves the **dd** command and **sudo**. This is **VERY DANGEROUS** - please do not run it unless you have read and fully understood what it will do. Better yet, read the scripts to learn how to install the image manually.

## Dependencies

- wget
- xz
- f2fs-tools (for mkfs.f2fs)
- dosfstools (for mkfs.vfat)
- rsync
- u-boot-tools (for mkimage)
- qemu-user-static (for qemu-aarch64-static)

## Usage

1. Edit `.env` with your own variables.
2. Run once `needed-programs.sh` to install all needed programs required to build.
3. Run `bash download-files.sh`. Be sure to run it at least once a day as kernel and rootfs are released daily.
4. Run `sudo bash all.sh`. Verify the information presented whenever it asks you to confirm.

## Tips

- Run all scripts other than download-files.sh as root, and from this (README.md) directory! Do not directly run anything in the phone-scripts folder! Those scripts are, as the name suggests, executed on the phone.
- If a script fails midway through, some things may still be mounted. `sudo ./cleanup.sh` will attempt to unmount everything.
