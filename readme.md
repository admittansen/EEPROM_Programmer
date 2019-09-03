# Installing the program

Just start sp300uw.exe and install it as any other program.

# Notes from Admittansen

 Follow bel text. To change the driver got to device manager and select the device (it appeared as unknown for me.), right click and click update driver. Then click the option that uses a local driver. Find the folder this text-file is contained in and let Windows search for driver in it. 

The hex editing should be done on the exe in the install location and not the one that installs the program. (Like dumb me first tried).

# Instructions from online source

N.B. This has only been tested on my PC using my Superpro 280u - it should work for you, but everything is done at your own risk!


Xeltek use a standard USB interface chip, an Ez-USB FX2, originally made by Anchor chips, who were taken over by Cypress.

Fortunately, they only seem to have made a single change to the reference driver that was issued by Anchor / Cypress, so as long as a 64 bit version of that driver exists then it should be possible to use the eeprom programmer on a 64 bit OS.

A clever guy (http://www.schemionneck.de/d500/tlbblog/) has already created a 64 bit version of the driver to use with some other hardware that utilises the same chip, and also sorted out the necessary inf files to allow you to install it on various newer versions of windows. A small change to that inf file, so it recognises the identity of the chip within the Superpro, and that will install the driver.

Another guy, Doug, has now signed the driver so that you no longer need to perform any weird changes to make Windows let you use the driver.

finally, you need to make one change to the SP3000.EXE to allow it to work with EZUSB.SYS (rather than their version XEUSB.SYS), and for this you will need a hex editor. I use XVI32, a free download from http://www.chmaas.handshake.de/delphi/freeware/xvi32/xvi32.htm. using this search for the text "Xeltekusb-0" (on the latest version it is at offset 9B344). This is the name of the driver that it is going to use, and so we need to change this to "Ezusb-0" and then pad the extra characters out with 00's (Hex 00, not characters!). Save this change and coupled with the driver you should now be able to use your Superpro on the 64 bit version of windows.


If you need XVI32 you will need to download it from their website.


For full information and any updates, check out my website, www.macros-arcade.com
