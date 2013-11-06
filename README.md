This is my first recovery, for MTK powered phones.

Basically is CWM 6.0.4.4 with touch buttons menu. It has all functionality of CWM Recovery, and I added extra, Aroma File Manager support.

The touch module is inspired mostly by <a href="https://github.com/scanno/CWM-Recovery-Modded-Touch-Vega">scanno touch recovery for Vega</a>, but also <a href="https://github.com/Napstar-xda/android_bootable_recovery">Napstar touch recovery</a>, and cleaned up and modernized with some stuff from <a href="https://github.com/ProjectOpenCannibal/android_bootable_recovery">Cannibal Open Touch Recovery</a>.

This is not a modified COT recovery. You won't find here settings or theme or some other cool stuff they created for COT recovery. For that go to COT Recovery source. I made this recovery to keep it simple and slim, because MTK phones have a limited size recovery partition. As I said, is a CWM modded recovery with touch screen menu buttons. Also I kept the Go Back entry in menu, just in case if for some devices is not working the touch menu - it will be just a good CWM recovery.

To compile you need a device folder for your phone, a cm-10.1 building environment and my source. 
<pre>Then just open "default_recovery_ui.c" and at line 46-47 and 53-54 do these settings:
```
*/
int maxX = "phone res width";	// for example  540
int maxY = "phone res height";	// for example  960	

/*
.....
*/
int resX = "phone res width + 14";	// for example  540+14=554	
int resY = "phone res height + 4";	// for example  960+4=964	

/*
```
==============================================================================================================
Also, in "ui.c" file set the following:
<pre>
```
#define CHAR_WIDTH 15  // accordingly to first value of the font used in BoardConfig.mk

#define CHAR_HEIGHT 30  // the second value of the font used in BoardConfig.mk, plus 4 or 6

#define MAX_ROWS 30  // divide "phone res height" to CHAR_HEIGHT value and the result decrease it with 2.
```
Enjoy!
