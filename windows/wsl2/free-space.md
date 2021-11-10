# Free up hard disk space occupied by WSL2 virtual disks

## Prerequisites

* Windows 10 Home
* WSL2

## Procedure

1. Terminate Docker Desktop
1. Close wsl terminal sessions
1. Run in the Windows Terminal
    ```
    wsl --shutdown
    wsl --list --running
    diskpart
    ```
1. To optimize Docker Desktop virtual disk, Run in the opened window with the command prompt `DISKPART>`
    ```
    select vdisk file="C:\Users\Santer\AppData\Local\Docker\wsl\data\ext4.vhdx"
    attach vdisk readonly
    compact vdisk
    detach vdisk
    exit
    ```
1. To optimize Ubuntu 20.04 virtual disk, Run in the opened window with the command prompt `DISKPART>`
    ```
    select vdisk file="C:\Users\Santer\AppData\Local\Packages\CanonicalGroupLimited.Ubuntu20.04onWindows_79rhkp1fndgsc\LocalState\ext4.vhdx"
    attach vdisk readonly
    compact vdisk
    detach vdisk
    exit
    ```
