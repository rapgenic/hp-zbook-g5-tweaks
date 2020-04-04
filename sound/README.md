# Sound codec fixes

The HP ZBook Studio G5 apparently has an undocumented **CX8400** Conexant Audio Codec, as is reported in BIOS information, which however works almost out of the box with the intel-hda-driver (generic codec, as the patch_conexant kernel module does not recognise this codec).

However, in the Conexant driver Windows inf file (`C:\Windows\System32\INF\oem62.inf`) it's named **CX2077x5**. Looking in that file we can see that the most relevant sections is `HdAud2077x.3DMic.AddReg`. There we can infer some of the additional default pin functions which the intel generic codec driver does not know:

| PIN  | Function                |
|------|-------------------------|
| 0x17 | Rear speakers           |
| 0x1f | Back-lid 2nd microphone |

Those have been added to the `[pincfg]` of the patch firmware for intel hda driver, and allow at least the rear speakers to be recognised. The secondary microphone is still not recognised by default.

# Mute LEDs

Mute leds do work actually, but they are not configured nor handled by the intel hda module (they can be tested however with hda_analyzer). Mute LEDs GPIOs are

| GPIO | Function |
|------|----------|
| 0x10 | Mute     |
| 0x20 | Mic mute |

# Installation

The firmware `hpzbsg5.fw` must be placed in `/lib/firmware` or where your linux distro stores the firmware files.

The module configuration file must be placed in `/etc/modprobe.d` for the module to correctly load the patch firmware file.