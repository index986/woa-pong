<img align="right" src="https://github.com/govro150/blob/main/pong.png" width="350" alt="Windows 11 running on pong">

# Running Windows on the Nothing Phone (2)

## Partitioning your device

### Prerequisites
- A brain (most important of all)

- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)
  
- [OFOX ( TWRP analogue )](https://dl.orangefox.download/65cb8503a53316f6742da34b)

- [Parted](https://github.com/n00b69/woa-polaris/releases/download/Files/parted)

### Notes
> [!WARNING]  
> Do not run the same command twice unless specified.
> 
> DO NOT REBOOT YOUR PHONE! If you think you made a mistake, ask for help in the [Telegram chat](https://t.me/woa_pong).
> 
> Do not run all commands at once, execute them in order!
>
> YOU CAN BREAK YOUR DEVICE WITH THE COMMANDS BELOW IF YOU DO THEM WRONG!!!

#### Flash TWRP recovery
> Open a CMD window inside the platform-tools folder, then (while your phone is in fastboot mode) run
```cmd
fastboot flash recovery path\to\twrp.img reboot recovery
```

#### Backing up important files
Use TWRP now to back up your Modem and EFS partition (as well as anything else if you have important data). Move this backup to a safe place (e.g your PC) as the next steps will wipe your data.

> [!Warning]
> All of your data will be erased. This is your last chance to back up.
> 
> **IF YOU PROCEED WITHOUT BACKING UP MODEM AND EFS, YOU ARE ON YOUR OWN IF YOU MESS UP**

### Partitioning guide
> Your Nothing Phone (2) may have different storage sizes. This guide uses the values of the 512GB model as an example. When relevant, the guide will mention if other values can or should be used.

#### Unmount data
- Go to "Mount" in TWRP and unmount data, if it is mounted

#### Preparing for partitioning
> Download the parted file and move it in the platform-tools folder, then run
```cmd
adb push parted /cache/ && adb shell "chmod 755 /cache/parted" && adb shell /cache/parted /dev/block/sda
```

#### Printing the current partition table
> Parted will print the list of partitions, userdata should be the last partition in the list.
```cmd
print
```

#### Removing userdata
> Replace **$** with the number of the **userdata** partition, which should be **13**
```cmd
rm $
```

#### Recreating userdata
> Replace **7837MB** with the former start value of **userdata** which we just deleted (it is probably 7837MB)
>
> Replace **505GB** with the end value you want **userdata** to have 
```cmd
mkpart userdata f2fs 7837MB 392GB
```

#### Creating ESP partition
> Replace **392GB** with the end value of **userdata**
>
> Replace **392GB** with the value you used before, adding **1GB** to it
```cmd
mkpart esp fat32 392GB 393GB
```

#### Creating Windows partition
> Replace **393GB** with the end value of **esp**
>
> Replace **505GB** with the end value of your disk, use `p free` to find it
```cmd
mkpart win ntfs 32.3GB 505GB
```

#### Making ESP bootable
> Use `print` to see all partitions. Replace "$" with your ESP partition number, which should be 14
```cmd
set $ esp on
```

#### Exit parted
```cmd
quit
```

#### Formatting data
- Format all data in TWRP, or Android will not boot.
- ( Go to Wipe > Format data > type yes )

#### Check if Android still starts
- Just restart the phone, and see if Android still works


## [Next step: Installing Windows](https://github.com/Project-Silicium/WoA-Guides/blob/main/Mu-Qcom/OS/Windows/Win.md#installing-step-3)
## [Last step: Setting up dualboot]()





















