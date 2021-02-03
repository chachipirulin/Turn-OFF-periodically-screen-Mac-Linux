# TurnOFF-screen-for-Mac-Linux
Turn OFF mac screen each 30 min (stand up and stretch time/seconds!). The screen will turn ON if you press any key.



Super easy:
            0 REQUIREMENTS 
            1 DOWNLOAD FILES
            2 DRAG AND DROP
            3 OPEN TERMINAL TO "LAUNCH" THE TURNOFF PROGRAM 
            4 CHECK IF PROCESS IS RUNNING AND DISABLE IT 
            5 EXTRA: PERSONALIZE TIME INTERVAL

0 REQUIREMENTS: INSTALL BREW AND LAUNCHTL

Follow the steps in: https://brew.sh/ to install Brew.
Afterwards, you need to install launchctl. for doing that, open your terminal and type the following:

            brew instal launchctl


1 DOWNLOAD FILES

 Download these two files (com.turnOff.plist & turnOff.sh) from this link:
              https://github.com/chachipirulin/TurnOFF-screen-for-Mac-Linux/archive/main.zip
            

2 DRAG AND DROP

Drag and drop the downloaded files into

            ~/Library/LauchAgents folder of your MAC.

3 OPEN TERMINAL TO "LAUNCH" THE TURNOFF PROGRAM (FOREVER RUNNING, NO NEED TO INITIATE EACH TIME)

Open terminal program and type:

      cd ~/Library/LauchAgents
      chmod a+x turnOff.sh
      ./turnOff.sh    
      launchctl load -w /Library/LaunchAgents/com.turnOff.plist

4 CHECK IF PROCESS IS RUNNING AND DISABLE IT (IF YOU WANT)

To check if the process is running, type the following line in the terminal and search through if "turnOff.sh" appears:

        launchctl list


To disable the ongoing background process (turning off the screen), unload the program typing the following line in the terminal:

        launchctl unload -w /Library/LaunchAgents/com.turnOff.plist
        
5 EXTRA: PERSONALIZE TIME INTERVAL  

To personalize time interval, just open "com.turnOff.plist" with a text editor (ie: TextEdit) and change the number that is in line:
      
            <integer>1800</integer>

and write how many seconds you want as interval to turn off screen and save the file
