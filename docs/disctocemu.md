How to dump a Disc Title for use on CEMU:  
(this guide assumes your system was already modded, if it is not follow [this](https://wiiu.hacks.guide) then come back here)

##What you need  
disc2app (it is on the Homebrew Appstore, or you can download it manually from [here](https://github.com/koolkdev/disc2app/releases/))  
[cdecrypt](https://github.com/VitaSmith/cdecrypt/releases)  (if you are on Linxu/macOS you will need to compile from source)  
The disc of the game you want to dump  

## Instructions

1. Install disc2app through one of the methods listed above.  
- Take out the disc you want to dump.  
- Load disc2app from the Homebrew Launcher and Press the  A button to start dumping.  
- Insert the disc.  
- Wait for it  to finish dumping.

## After dumping

1. Insert the SD into your PC.  
- Copy the `WUP-X-XXXX` from the install folder on the sd root to somewhere to your PC.  
- Extract the `cdecrypt.exe` file from the `cdecrypt.zip` to the `WUP-X-XXXX` folder.  
- Hold shift and right click. Open up a windows powershell.   
- Type  in `.\cdecrypt.exe title.tik`. 
- There should now be `code content meta` folders.
- Install the game in CEMU.
- After installing, delete the game from your PC. 