## Mountain Lion 10.8.5

### AppleHDA 2.4.7<br />
Here, we use a modified kext.<br />
Patch the binary: Find »8b19d411« and replace it with »6950f114«.<br />

- Replace the Info.plist in PlugIns/AppleHDAHardwareConfigDriver.kext/Contents/
- Generate a layout3.xml.zlib from the layout3.xml and place it in Resources.
- Generate a Platforms.xml.zlib and place it in Resources, too.

Install the AppleHDA.kext in S/L/E, clear the caches and reboot.
