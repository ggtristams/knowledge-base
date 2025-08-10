Troubleshooting: The Last of Us Part I (Epic Games) – Repetitive Visual C++ Installation
Issue: When attempting to launch The Last of Us Part I through the Epic Games Launcher from ggLeap client, the game repeatedly tries to install the Visual C++ Redistributable (VC++), preventing the game from launching correctly. This can happen even if the necessary VC++ versions are already installed on your system.

Root Cause (Suspected): The game's pre-launch script (prelaunch.bat) might be incorrectly configured to force a VC++ installation on every launch, regardless of its installed status. Additionally, ggLeap’s lockdown policies might be interfering with the Visual C++ installation process by modifying or blocking necessary registry entries or system access required for the installation to complete successfully. This interference can lead to the game continuously attempting to re-install VC++ without success.

Resolution: To resolve this, you need to modify a setting within the prelaunch.bat file to prevent it from forcing the VC++ installation.

Steps:

Navigate to the Game Installation Directory:

Open the Epic Games Launcher.

Go to your Library.

Locate "TheLastofUsParti."

Click the three dots next to the game title.

Select "Manage."

Under "Installation," click the folder icon next to "Installation Location" to open the game's directory in File Explorer.

Locate the prelaunch.bat file:

Once in the game's installation directory, look for a folder named TheLastOfUsPartI.

Edit prelaunch.bat:

Right-click on the prelaunch.bat file.

Select "Edit" (this will usually open it in Notepad or a similar text editor).

Modify the NeedInstall variable:

Inside the prelaunch.bat file, look for a line that contains set NeedInstall=TRUE.

Change TRUE to FALSE. The line should now read:

set NeedInstall=FALSE
Important: Ensure you only change TRUE to FALSE and do not alter any other part of the line or file unless you are absolutely sure of its purpose.

Save the changes:

After making the change, save the prelaunch.bat file (File > Save or Ctrl + S).

Launch the game:

Close the prelaunch.bat file.

Attempt to launch The Last of Us Part I from the Epic Games Launcher again from ggLeap.

Expected Outcome: The game should now bypass the forced Visual C++ Redistributable installation and proceed directly to launching the game.

Additional Notes:
You need to at least complete the installation from admin mode before attempting to change the contents of the bat.