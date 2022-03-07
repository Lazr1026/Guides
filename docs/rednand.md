Welcome to my bad guide on Github Wiki thing  

this is an old guide. be warned if something doesnt work.  

## What you need:

An already modded Wii U (that being with Mocha, Haxchi, or CBHC)  
A big enough SD Card (64GB+)  
[Mocha CFW](https://www.wiiubru.com/appstore/zips/mocha.zip) (You can skip this if you've modded your Wii U with Mocha.)  
[config.ini](https://github.com/Lazr1026/Guides/blob/main/files/rednand/config.ini) (You can skip this if you've modded your Wii U with Mocha.)  

### SD Card setup

1. Copy the ``wiiu`` folder from the ``mocha.zip`` to the root of your SD Card.

2. Copy the ``config.ini`` to ``wiiu/apps/mocha`` on your SD Card.

3. Make a copy of your entire SD Card to a safe place on your PC as it will be formatted.

## redNAND setup

1. Insert the SD Card into your Wii U.

2. Launch ``Mocha CFW``  
- CBHC: Click on the CBHC icon and press the HOME button when you see the ``Autobooting...`` screen and choose ``Mocha CFW``.  
- Haxchi: Launch Haxchi while holding the A button. This should load the HBL. After HBL has been loaded navigate to ``Mocha CFW`` and select ``Load``.  
- Mocha: Launch the [HBL](https://wiiu.hacks.guide/#/vwii/browser-exploit) and load ``Mocha CFW``.

3. You will see a screen that says to format your SD Card, press the POWER button on your Wii U to do so.

4. After that you will have to wait for the redNAND to be created. (This will take 30m-2hr depending on your model.)

5. When it is done you should boot into redNAND. Turn off the console for now.

6. Put your SD Card in your PC and copy all the files you backed up before formatting the SD Card.

You're done! You have now made a redNAND for god knows why.

##Notes  

Note for CBHC Users: You can press the HOME button when you see the ``Autobooting...`` screen to then select ``Mocha CFW`` to boot 
into redNAND  

Note for Haxchi Users: You can edit your config.ini in ``sd:/haxchi`` to have it load up mocha when you open the app automatically/hold a button.

Note for Mocha Users: You can hold B while loading Mocha to then chose whether if you want to boot redNAND or not. (No boots to sysNAND, Yes boots to redNAND.)  

Note for all Users: You cannot use the vWii in any way (such as Wii/GCN injects or the Wii Menu).

Credits:
kudos to dimok for Mocha CFW and Fix94/smealum for Haxchi/CBHC (and Gary for the idea of making a redNAND guide)
