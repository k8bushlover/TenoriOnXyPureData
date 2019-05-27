# TenoriOnXyPureData
Tenori-On XY controller

To allow Tenori-On grid on any layer to control two parameters (Volume, Pan) on designated channels. Original intention was for Tenori-On to control itself (one layer being used to control others), Tnr OUT->Puredata->Tnr IN.

Pure Data patch is to intercept sysex messages indicating XY 16x16 grid button press positions on Tenori-On.  Channel to receive X (Volume) and Y (Pan) can be set separately in the patch. Assigns Expression and Panpot as the X-Y controllers, this could be enhanced for flexibility, with appropriate adjustments to calculations for other controllers. (Tenori-On recognizes only a few controllers, though; apps recognize pitch bend and sustain, not documented in MIDI chart; h/w accepts sustain as well. Sysex out is independent of any channel on Tenori-On.)  

For Tenori-On-ists: Tries to toggle on/off whether to send MIDI out based on whether a FRAME button press (L1-L5, R1-R5) is in effect, toggling OFF when a Frame button is pressed, ON when released.  So, be careful to release the GRID button presses BEFORE releasing the FRAME buttons, to avoid sudden jumps in controller outputs.

Used GUI elements only on main patch with sends/receives to the subpatch. (For use with pdParty on iOS as well, which has been updated to include virtual ports.)  Although subpatch's loadbang in pdParty doesn't initialise the parent patch's number boxes for MIDI channel to 1 instead of 0, this is a minor detail probably better solved by better programming on my part.)

syx2list abstraction to receive sysexin bytes, output as list when complete 240-247 (F0-F7) message is constructed

tnrsyx abstraction uses syx2list to return data1, data2, data3 bytes of Tenori-On Sysex messages 
