SharpQuake 1.3 release notes

--------------------------------------------------------------------------------
Building and running
--------------------------------------------------------------------------------

To build project successfully, define correct reference to OpenTK library (see References).

To build with Windows-related stuff add _WINDOWS symbol to "Conditional Compilation Symbols" (there must be already defined GLQUAKE and QUAKE_GAME symbols).

On x64 platforms select x86 as a Platform.

To run from any folder except Quake's one add -basedir switch and correct path to your directory of Quake (for example, if Quake is installed in C:\Games\Quake):
SharpQuake.exe -basedir C:\Games\Quake

To run from IDE go to the Project Properties -> Debug tab -> Start Options. In "Command line arguments" edit box add -basedir switch 
and correct path to your directory of Quake (for example, if Quake is installed in C:\Games\Quake):
-basedir C:\Games\Quake

To run in windowed mode add -window command line switch.

If you have original mod packs (from Rogue or/and from Hipnotic) run them with appropriate switch: -rogue or -hipnotic

All mentioned switches are original GLQuake's switches, so please see the docs for details.


--------------------------------------------------------------------------------
Notes
--------------------------------------------------------------------------------
1) If mouse is not working in windowed mode, please check value of cvar _windowed_mouse - this should be "1". 
For example, Steam version of Quake have autoexec script which resets this to 0.

--------------------------------------------------------------------------------
Fixed bugs
--------------------------------------------------------------------------------

1) Audio initialization bug: sometimes program starts without sound and (with developer=1) there is a 3 messages in console:
UnlockBuffer: No free buffers!
UnlockBuffer: No free buffers!
UnlockBuffer: No free buffers!

2) Wrong index returned by String.IndexOf () in ProgsEdict.cs on Linux (reported by Miguel G L):
For example, on Linux String.IndexOf() returns an index "offset = 6633" in the case of Windows "offset = 6632". The correct value is 6632

3) OpenTK version updated to 1.1

Enjoy!