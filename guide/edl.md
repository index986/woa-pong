<img align="right" src="https://github.com/govro150/woa-pong/blob/main/pong.png" width="350" alt="Windows 11 running on pong">

# Running Windows on the Nothing Phone (2)

## Restoring your device with EDL

### Prerequisites

- [EDL tools](https://drive.google.com/file/d/1dfW2pNLxn8d-4sV7FQ9n-nKfreRjyWan/view?usp=sharing)

- [EDL drivers](https://xdaforums.com/attachments/qualcomm-hs-usb-qdloader-9008-driver-zip.6081556/?hash=59c2fd14784d4b8b66600e964459c427)


### Booting into EDL mode
> If you're already in EDL, you can skip this step
- Download and extract **Nothing_1.4_MOD.7z**. You may need to disable your antivirus software or it may falsely be detected as being malware.
- In android do this: adb reboot edl
- Open **NothingFlashTool.exe**.
- Press **2**, then confirm by pressing **enter** to boot into EDL mode.

#### Finding the COM## number
> The software should open device manager. If it does not, open it manually
- Locate a device named **Qualcomm HS-USB QDLoader 9008 (COM##)** under **Ports (COM & LPT)**.
> [!Important]
> If the device has a ⚠️ yellow warning triangle, you need to install EDL drivers before you can continue to the next step.
- Record the **COM##** number at the end of **Qualcomm HS-USB QDLoader 9008 (COM##)**.

#### Reboot to Android
> After it finishes flashing the ROM (this might take around 5 minutes), simply reboot the device to boot back into Android.

## Finished!












