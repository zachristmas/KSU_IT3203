**Lab Setup FOR MAC**

_Note: everywhere in the instructions where you see_ **_USERID_**_, replace with your KSU NetID username (not including the @students.kennesaw.edu)_

**Initial SSH test:**
-   Start setting up SSH connection to the school
	-   In the terminal console type: ``ssh USERID@weblab.kennesaw.edu``
	-   Confirm “yes” to trusting ssh certificate
	-   Enter your NetID password
	-   You should see a long message about legal responsibilities and whatnot
-   Validate web lab files
	-   In the same terminal, type: ``ls``
		-   You should see: ``public_html``
	-   Enter the public_html directory with the following command: ``cd public_html``
	-   To validate your web page is there, type: ``ls``
		-   You should see: ``index.html``
	-   To view the contents of your webpage, type: ``nano index.html``
		-   You should see the html text here, to quit the editor on Mac press: ``ctrl + x``
-   Now logout of weblab terminal by typing: ``logout``

Success! You can access the weblab!

**Linking Weblab server to your mac**
-   Start by installing home-brew for Mac (if not already installed)
	-   Open ‘Terminal’ application
	-   Paste this into the terminal console (including quotes): ``/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"``
-   Now install fuse and sshfs:
	-   Paste this into the terminal console: ``brew cask install osxfuse``
		-   **NOTE:** osxfuse requires a kernel extension to work. If the installation fails, retry after you enable it in:  System Preferences → Security & Privacy → General
	-   After that completes **RESTART** the computer, open terminal again, and paste this into the terminal console: ``brew install sshfs``
-   Next, we SSH to the school weblab and mount the folder to our Mac
	-   Paste this into the terminal, replace the USERID with your KSU NetID: ``sudo sshfs -o allow_other,defer_permissions,IdentityFile=~/.ssh/id_rsa USERID@weblab.kennesaw.edu:/home/USERID/ /localfolder``
		-   The first password it prompts you for is your computer password
		-   The second password it prompts you for is your KSU NetID password
-   The ssh server should be connected to your Mac.
	-   To view the files, **open the ‘Finder’ application on your Mac**
	-   In the top menu, select **Go -> Computer**
	-   **Double-click OSXFUSE**, and you should see the same public_html folder that we saw in the SSH test
-   **Open ‘Textedit’** application on your Mac
	-   Go to Textedit preferences by pressing (**Command + comma)** or **Select ’Textedit’ on the top menu and select ‘Preferences’**
	-   **Select the ‘Open and Save’ tab**
	-   **Check ‘Display HTML files as HTML code instead of formatted text’**
	-   **Close out of TextEdit**
-   Now go back to the **OSXFUSE -> public_html** folder in finder
	-   Right-click the index.html file and select **‘Open With’**
	-   Select **’TextEdit’**
	-   Make any changes you would like and **save the file**

-   Visit https://weblab.kennesaw.edu/~USERID/
	-   You may be prompted to enter your NetID username and password (not including the @students.kennesaw.edu)
	-   It kept on spinning for me at this stage after entering login information, I had to refresh a couple times to get the page display

  

Success! You shouldn’t have to use the terminal any more, simply edit the files directly on the OSXFUSE folder

  

**NOTE: If you log out, shutdown, or restart your Mac, you will need to repeat the following steps to connect weblab to your Mac again:**
-   SSH to the school weblab and mount the folder to our Mac
	-   Open terminal and paste this, replace the USERID with your KSU NetID: ``sudo sshfs -o allow_other,defer_permissions,IdentityFile=~/.ssh/id_rsa USERID@weblab.kennesaw.edu:/home/USERID/ /localfolder``
		-   The first password it prompts you for is your computer password
		-   The second password it prompts you for is your KSU NetID password

  

_I would highly recommend saving that command with your USERID somewhere that can easily be copied and pasted into the terminal to save time._
