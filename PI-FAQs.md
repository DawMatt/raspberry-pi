1) How do you enable remote access to the command line?

Raspbian includes the SSH daemon by default but it isn't turned on. Use the Preferences/Raspberry Pi Configuration menu item to enable SSH (via the Interfaces tab).

This can also be enabled from the command line using sudo raspi-config

2) How do you enable remote access to the desktop?

Raspbian includes the VNC daemon by default but it isn't turned on. Use the Preferences/Raspberry Pi Configuration menu item to enable VNC (via the Interfaces tab).

This can also be enabled from the command line using sudo raspi-config.

Any VNC client should be able to remotely access the desktop, assuming the desktop is still enabled. If the Boot options is set to "Console Only" then VNC will connect but nothing will be displayed.

3) How do you remotely access desktop applications from a macOS system?

macOS no longer includes X11 by default. Use XQuartz ( https://www.xquartz.org/ ) to install an X Windows sub-system to allow your Pi's desktop applications to be installed.

Once this has been enabled and you have logged out and back in, you need to set your DISPLAY environment variable appropriately on your Mac. e.g. 
export DISPLAY=:0.0

Use ssh with the -Y option to allow forwarding of X11 displays. e.g. 
ssh -Y pi@raspberrypi

To test the connectivity run an X11 application and it should appear on your Mac systme. e.g. 
xpdf
