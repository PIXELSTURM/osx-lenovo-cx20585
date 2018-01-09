## AppleHDA CX20585 Codec V1.0
<br />
This is a working Conexant CX20585 AppleHDA-Codec for Lenovo-Laptops like T410/T510 and others.<br />
V1.0 due to the fact it's not perfect and hdmi support is missing.


First of all: HDA-Codec hacking is a pain!

<br />

![release-img](pix/preview.png)

<br /><br />

## History
After using pre-modified kexts for a long time i decided to make my own *working* one.<br />

First you've to dump the codecs from linux or windows.<br />
With the help of different tools you'll get this:

[![structure-img](pix/codec-dump.png)](pix/codec-dump.png)

These informations are used to make the audio mapping and the pin-configuration.

<br /><br />

The result looks like this:

![release-img](pix/ports.png)

![release-img](pix/intmic.png)

![release-img](pix/extmic.png)

Working features:<br />
- internal mic<br />
- internal speakers<br />
- headphones<br />
- combo jack sensing (external mic/headphone)<br />
- ambient noise reduction<br />
- mic volume for the ext mic<br />
- mute<br />

This release works, but is not complete. I.e. the input-volume of the internal microphone is not working, but it's set to a useable value.

Tested with Mountain Lion, Yosemite and El Capitan.
<br /><br />

## Howto
1. Make sure your system uses the audio layoutID 3.<br />
This could be happen i.e. via bootloader, custom dsdt or an enabler kext.<br />

2. The AppleHDA.kext<br />
For ML i use a patched kext.<br />
For YO and EC a dummy kext is my first choice.<br />
AppleHDA binary is patched on the fly via bootloader (Find: 8B19D411 / Replace: 6950F114).<br />

- Patch to use the right codec-id.<br />
- Insert pin-configuration.<br />
- Insert id 3 mapping.<br />
- Insert mapping data to the platform.xml.<br />

Don't forget to clean the caches before reboot!
<br /><br />

Have fun!

