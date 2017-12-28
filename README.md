# TenoriOnXyPureData
Tenori-On XY Pure Data controller

Assumes Tenori-On (or iOS apps TNR-i or TNR-e) is connected via MIDI interface to PC, pure data patch is to intercept sysex messages indicating XY 16x16 grid button press positions on Tenori-On.  Channel to receive X (Volume) and Y (Pan) can be set separately.

Set up to use Expression and Panpot as the X-Y controllers, this could perhaps be enhanced for some flexibility.  (Sysex out is independent of any channel.)  

Used GUI elements only on main patch with sends/receives to the subpatch. (For use with pdParty {or MobMuPlat?} on iOS as well, with some creative MIDI 'cabling' and filtering through midiflow -- otherwise apps' MIDI ports can't be seen at all by pdParty.  Although subpatch's loadbang in pdParty doesn't serve to set the parent patch's number boxes for MIDI channel to 1 instead of 0, this is a minor detail probably better solved by better pure data programming on my part.)

Not perfect--subpatch not always toggling off in time to prevent higher values from reaching the respective ctlout objects.  

syx2list abstraction could MAYBE use a 1 ms delay before the 'bang' to output the list (latter 247 sometimes not added to list and sent from abstraction, although the calling patch doesn't really need it.)
