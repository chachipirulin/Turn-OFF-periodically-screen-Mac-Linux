# TurnOFF-screen-for-Mac-Linux
Turn OFF mac screen each 30 min (stand up and stretch time/seconds!)
(or personalize which is the time interval)


Super easy:
1 DOWNLOAD FILES
2 DRAG AND DROP
3 OPEN TERMINAL TO "LAUNCH" THE TURNOFF PROGRAM 
4 CHECK IF PROCESS IS RUNNING AND DISABLE IT 

1 DOWNLOAD FILES
Download these two files (com.turnOff.plist & turnOff.sh) from this link:

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
