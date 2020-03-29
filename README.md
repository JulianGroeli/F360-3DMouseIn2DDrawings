# F360-3D-Mouse-navigation-in-2D-Drawings

I created this project because I couldn't find another way to use my Spacemouse in Fusion 360's 2D Drawing mode.

The need for this is covered in more detail on the archived Fusion 360 IdeaStation posts here:
https://forums.autodesk.com/t5/fusion-360-ideastation/add-3d-mouse-support-in-drawing-mode/idi-p/6502859
https://forums.autodesk.com/t5/fusion-360-ideastation/pan-and-zoom-with-3d-mouse-in-2d-drawing/idi-p/9063688

This project uses configuration files for the Spacemouse to send panning and zooming navigation commands to Fusion 360. Since Fusion 360 doesn't have a published API for 2D drawings mode, these configuration files set up the spacemouse to emulate a regular 2D mouse.
- AcCoreConsole.xml contains the configuration for 2D navigation in 2D drawings mode.
- Fusion360.xml contains the configuration for 3D navigation in Fusion's other modes: design, generative design, render, animation, simulation and manufacture. 

Thanks to jwick on the 3D Connexion blog, without whom this would not have been possible. Please see the below thread and post comments and feedback here:
https://www.3dconnexion.com/forum/viewtopic.php?f=25&t=39216

Current functionality:
- smooth 2D panning around drawings
- somewhat jerky, but still usable zooming in and out of drawings
- automatic loading of the 2D navigation configuration for drawing mode
- automatic loading of the 3D navigation configuration for design mode

Tested platforms:
- Win10 x64, using 3DxWare 10.6.0, 3DxWinCore 17.6.0.16266

How to install:
- Download the .xml configuration files
- Quit Fusion 360 if it's running
- Stop the 3Dx Service
- Copy the .xml configuration files to your cfg directory: %appdata%\3Dconnexion\3DxWare\Cfg
- Start the 3Dx Service
- Start Fusion 360

Known issues:
- The mouse moves while panning. If the mouse moves out of the drawing window while panning you have to move it back with the regular 2D mouse.
- Fusion has a hard-coded keyboard short cut to "zoom to fit" on double click of the middle mouse button. This can be accidentally triggered by two very short panning moves.
- If configuration files are edited in a text editor (eg notepad++), with the 3Dx service stopped but Fusion 360 still running, the 3D navigation mode does not work (no movement) once the 3Dx service is restarted. Once Fusion 360 is restarted it works again.

To do:
Update driver and update these configs to 1.3. The 1.2 versions are posted below if someone needs them.

Feedback and comments are most welcome.
