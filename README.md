# Turn OFF periodically screen (ONLY INSTRUCTIONS FOR MAC)
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
Afterwards, you need to install launchctl. For doing that, open your terminal and type the following:

            brew install launchctl-completion


1 DOWNLOAD FILES

 Download these two files (com.turnOff.plist & turnOff.sh) from this link:
              https://github.com/chachipirulin/TurnOFF-screen-for-Mac-Linux/archive/main.zip
            

2 DRAG AND DROP

For MAC:

Drag and drop the downloaded files into the LauchAgents folder of your MAC (LaunchDaemons folder could also work). That folder usually is located following the next path:

            ~/Library/LauchAgents
            
("~" means the root of your system, normally, its name is smth like "JohnMacBookPro", "MyMacBook" or "Macintosh HD")

For Linux:


Drag and drop the downloaded files into the init folder. That folder usually is located following the next path:

            ~/etc/init 
If your Linux does not allow you to drag and drop these files, please, use terminal command "mv" to move this files into the folder.
Search "move files using terminal linux" on your favourite web browser to find how if you do not know how. In my case, I opened the terminal and I just needed to type the two following sentences to move the two download files my terminal (notice that I pu the downloaded folder into my Desktop "Escritorio"):

      sudo mv ~/Escritorio/Turn-OFF-periodically-screen-Mac-Linux-main/turnOff.sh /etc/init/
      sudo mv ~/Escritorio/Turn-OFF-periodically-screen-Mac-Linux-main/com.turnOff.plist /etc/init/


3 OPEN TERMINAL TO "LAUNCH" THE TURNOFF PROGRAM (FOREVER RUNNING, NO NEED TO INITIATE EACH TIME)

For Mac, open terminal program and type:

      cd /Library/LauchAgents
      chmod a+x turnOff.sh
      ./turnOff.sh    
      launchctl load -w /Library/LaunchAgents/com.turnOff.plist
      
(if first line does not work, type "cd NAME_FOLDER" to move where you "Library" folder is. "cd" stands for change directory = clicking on a folder will move you to the conect of that folder, this is exactly the same but using the terminal)

For Linux, open terminal program and type:

      cd /Library/LauchAgents
      chmod a+x turnOff.sh
      ./turnOff.sh    
      launchctl load -w /Library/LaunchAgents/com.turnOff.plist
4 CHECK IF PROCESS IS RUNNING AND DISABLE IT (IF YOU WANT)

To check if the process is running, type the following line in the terminal and search through the output (whatever is written on the terminal after running the line) if "turnOff.sh" appears:

        launchctl list


To disable the ongoing background process (turning off the screen), unload the program typing the following line in the terminal:

        launchctl unload -w /Library/LaunchAgents/com.turnOff.plist
        
5 EXTRA: PERSONALIZE TIME INTERVAL  

To personalize time interval, just open "com.turnOff.plist" with a text editor (ie: TextEdit) and change the number that is in line:
      
            <integer>1800</integer>

and write how many seconds you want as interval to turn off screen and save the file.

Hope it works for you! It works like a charm for me :)
