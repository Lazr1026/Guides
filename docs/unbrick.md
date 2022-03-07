Hello and welcome to the new and improved ~~freddy fazbears pizza~~ Wii U Unbrick Guide. This Guide only covers the SLC (Wii U).  

Usually if you need to restore vWii NAND, there is [vWii NAND Restorer](https://gbatemp.net/threads/release-vwii-nand-restorer.560948/) (Needs backup) or [vWii Decaffenator](https://gbatemp.net/threads/vwii-decaffeinator-restore-vwii-without-a-nand-backup.566252/) (Doesn't need backup)

Wii U doesnt have something like that yet though... so we have to open up the console and solder some wires to the NAND.

To unbrick the Wii U we will use an Rasberry Pi. I have only ever used an RPI0 but the pinouts should be the same on every RPI. If you want to use a Teensy to unbrick, refer to [this guide](https://gbatemp.net/threads/guide-kaflukes-hardmod-cbhc-unbrick-guide.476725/)

## What you need
- An slc.bin dump from *before* the brick, or an otp.bin dump.  
- A Raspberry Pi and MicroSD for the Raspberry Pi.  
- Decent soldering equipment.  
- Decent soldering skills.  
- Ability to follow instructions.  
- A Lot of time.  
- A Decent understanding of Linux.
- Last but not least, A Brain.

### Setting up the software
1. Set up RPIOS on a MicroSD. (Guide: [https://www.raspberrypi.com/documentation/computers/getting-started.html](https://www.raspberrypi.com/documentation/computers/getting-started.html))
- Power on your RPI and connect it to the internet.  
- Open up a terminal (`CTRL ALT T`), run `wget https://raw.githubusercontent.com/Lazr1026/Guides/main/files/unbrick/pinand.sh && chmod +x pinand.sh`.  
- Now run `./pinand.sh`.

### Solder the RPI to Wii U board
1. Take apart the Wii U, look up a teardown.  
- Make sure you are VERY CAREFUL when soldering to these points. one mess up and your console may be dead for good.  
Solder Points:  
RPI:  
![](https://github.com/Lazr1026/Guides/raw/main/files/unbrick/pinout.png)  
Wii U Board:  
![](https://github.com/Lazr1026/Guides/raw/main/files/unbrick/solder.jpg)

- It should look like this when finished. Use that pad off to the side as `GND`.  
(Taken from Kaflukes CBHC Hardmod Guide)  
![](https://github.com/Lazr1026/Guides/raw/main/files/unbrick/done.png)

## Fixing the NAND

Note: Now depending on what the hell you did, you could be doing something WAY different. We will be fixing a CBHC Brick here.  

### FIXING THE NAND WITH ONLY OTP.BIN  

Download [Eyekeys NAND Tools](https://github.com/koolkdev/wiiuqt/releases/tag/v0.2) and extract the zip somewhere on your PC.

1. Put the Wii U back together enough to get everything plugged in (Disc Drive, Power Button, Fan, Heatsink.)  
- Power on the Wii U.  
- Turn on the RPI.  
- Open up a terminal and run `sudo ./pinand 50 read_id`, you should get something like this.  
![](https://raw.githubusercontent.com/Lazr1026/Guides/main/files/unbrick/readid.jpg)
- Run `sudo ./pinand 50 read_full 0 262144 slc.bin`.  
- Wait for it to finish reading. (DO NOT UNPLUG THE WII U OR RPI.)  
- Turn off the Wii U and RPI, insert the RPI' MicroSD in your PC.  
- Copy the `slc.bin` from `sd:/home/[USER]` to the NAND Tools folder on your PC. (Hint: Now would be a REALLY good time to copy otp.bin to the folder as well.)  
- Open a Command Prompt and run `nandCbhcRemover.exe slc.bin`. 
See the next section for flashing the NAND back to the Wii U.

### FIXING THE NAND WITH ONLY SLC.BIN  
1. Insert the RPI' MicroSD in your PC.  
- Copy `slc.bin` to `sd:/home/[USER]`. (OTP Only Users: Click `Replace` when asked.)  
- Insert the RPI' MicroSD into the RPI.  
- Turn on the Wii U.  
- Turn on the RPI.  
- Open a terminal and type in `sudo ./pinand 50 read_id`. You should get something like this.  
![](https://github.com/Lazr1026/Guides/raw/main/files/unbrick/readid.jpg)  
- Run `sudo ./pinand 50 erase_blocks 0 4096 && sudo ./pinand 50 write_full 0 262144 slc.bin`.   
- Wait for it to finish, this will take a LONG time (around 2 days). (DO NOT UNPLUG THE WIIU OR THE RPI.)  

## After Flashing  
1. Turn off the Wii U.  
- Turn off the RPI.  
- Put the Wii U back together enough to test if it boots, plug in Disc Drive, Power Button, Fan, Heatsink.  
- Turn on the Wii U, connect an HDMI or AV (or if your Gamepad is still paired, that works too).  

-If it loads to Wii U Menu, congrats, desolder the wires on the Wii U Board and put the system back together. You have successfully done the RPI Hardmod Method.  
-If it does not load to Wii U Menu and Errors, then you did something wrong, or you used the wrong backup. Try Flashing again, or join [Ivy's Stuff](https://discord.gg/HNDcTEkcR3) and ask for help in `#help`
	
## Credits:  
Theres too many people to list, but if you have talked to me on discord chances are you have helped. Thank You All :).   