# TenoriOnXyPureData
Tenori-On XY Pure Data controller

Specifically set up to loop Tenori-On (or iOS apps TNR-i or TNR-e) MIDI OUT to its own IN, to intercept sysex messages indicating XY 16x16 grid button press positions on Tenori-On.  Channel to receive X (Volume) and Y (Pan) can be set separately.

Set up to use Expression and Panpot as the X-Y controllers, this could perhaps be enhanced for some flexibility.  (Sysex out is independent of any channel.)  

Used GUI elements only on main patch with sends/receives to the subpatch. (For use with pdParty or MobMuPlat? on iOS as well, although subpatch's loadbang doesn't serve to set the parent patch's number boxes for MIDI channel to 1 instead of 0.)

Not perfect--not always toggling off in time to prevent higher values from reaching the respective ctlout objects.  

syx2list abstraction could MAYBE use a 1 ms delay before the 'bang' to output the list (latter 247 sometimes not added to list and sent from abstraction, although the calling patch doesn't really need it.)
