<img align="right" src="https://github.com/govro150/woa-pong/blob/main/pong.png" width="350" alt="Windows 11 running on pong">

# Running Windows on the Nothing Phone (2)

## Additional materials
> Below you will find a list of tweaks and materials for Windows on your ARM device

### List of supported apps/games
This is by no means a comprehensive list, it simply lists apps/games that have been tested by the community
[The link can be found here](https://docs.google.com/spreadsheets/d/1XYuoySgYQE0HL573sA-0RGMX7I4lt5rWJuQ8Z8yRJNY/edit?usp=drivesdk)

You can also find a list of dedicated ARM software [at this link](https://armrepo.ver.lt/)

##### Finished!

### Hide D drive (modem partition)
> [!NOTE]
> This is recommended because this drive should not be modified, while some applications may try to write to it.

#### Automated method
- Download [ModemHide.vbs](https://github.com/Misha803/My-Scripts/releases/tag/ModemHide) onto your pong
- Run it
- Approve any UAC dialogs 
- Click `Yes` in the dialog box

#### Manual method
- Open a command prompt window and run ```diskpart```
- Run ```list volume``` to see all available volumes
- Select the disk that has letter D with ```select volume $```, replacing "$" with the volume number
- Remove the letter with ```remove letter d```
- Exit diskpart with ```exit```

##### Finished!


### Install Microsoft Office / Microsoft 365
- Download this [ISO file](https://mega.nz/file/hjAiSL4T#G7kOKpsUFpyL2UW9RQmY2e96urcQW5xZKdc7ciaNOy8) to the phone
- Right-click on the iso file and select Mount to open it in explorer
- Double-click on ```Office Tool Plus.exe``` to start the installation wizard
- Approve any UAC dialogs 
- In the window that appears, click `Yes` to start installation 
- Wait for the installation to complete

##### Finished!

### Activate Windows / Office
Follow the instructions by Massgravel [here](https://github.com/massgravel/Microsoft-Activation-Scripts)

##### Finished!





















