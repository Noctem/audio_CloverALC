![audio](https://github.com/Noctem/audio_CloverALC/raw/master/sound.png)
# audio\_cloverALC
Realtek ALC/Desktop: 269(1), 283(1), 885, 887, 888, 892, 898 and 1150 on board audio  (1) BRIX/NUC only
Supports OS X: 10.13, 10.12, 10.11, 10.10, 10.9 and 10.8
Native AppleHDA/Persistent

**OS X/Clover patched AppleHDA Realtek ALC Audio**

The Clover/kext patched Realtek ALC method enables OS X AppleHDA onboard audio with or without HDMI and DP audio. The script adds codec specific layout and platform files and injects binary patch and pin configuration data to the native installed AppleHDA.kext.

Clover version of Piker Alpha/AppleHDA8Series.sh. The script adds AppleHDA.kext kernel cache patches to config.plist and installs L/E/AppleHDAxxx.kext (xxx = codec)

**Updates**

1. 10/26/16 - 10.12 support
2. 7/15/16 - Initial 10.12 support, try -120 versions
2. 12/14/15 - audio_pikeralpha-110 (Clover version of Piker Aplha AppleHDA8Series.sh)
2. 11/8/15 - Skylake/Series 100 Update, Add 1150/Audio ID: 3
3. 7/19/15 - 283 Update
4. 6/15/15 - 10.11 - El Capitan Realtek ALC AppleHDA.kext Initial Support


**A. Installation**

1. Open Terminal
2. `git clone https://github.com/Noctem/audio_CloverALC.git`
3. `cd audio_CloverALC`
4. `./audio_cloverALC.sh`

**B. Requirements**

1.  OS X Versions (+ all)
    1.  10.13+/High Sierra
    2.  10.12+/Sierra
    3.  10.11+/El Capitan
    4.  10.10+/Yosemite
    5.  10.9+/Mavericks
    6.  10.8+/Mountain Lion
2. Boot Flags/Boot failure may result if ignored
	1.	10.11+/Disable SIP/set, restart, install, enable SIP, restart
		1.	CLOVER/config.plist/
			1. ACPI/DSDT/Fixes/NO (all or remove)
			2.	RtVariables/BooterConfig/0x28
			3.	RtVariables/CsrActiveConfig/0x3
	2.	10.10+/Allow unsigned kexts/set, restart, install
		1.	Clover/config.plist
			1. ACPI/DSDT/Fixes/NO (all or remove)
			2.	Boot/Arguments/kext-dev-mode=1
3.  [Native AppleHDA.kext](https://github.com/toleda/audio_ALC_guides/blob/master/Restore%20native%20AppleHDA%20%5BGuide%5D.pdf)
4.  Audio codec? See Tools 4.
5. 100/200 Series Audio Fixes (not macOS native, select one)
	1.	[config.plist edit:] (https://github.com/toleda/audio_CloverALC/blob/master/config-audio_cloverALC-120.plist.zip) ACPI/DSDT/patches/Item 0
	2. [ssdt enabler] (https://github.com/toleda/audio_ALCInjection/blob/master/ssdt_hdef/ssdt_hdef-1-100-hdas.zip)

**C. Realtek ALCxxx** - Verify, see Tools 4.

1.  Supported codecs (* Not supported with audio_pikeralphaALC)
    1.  269 (BRIX only) *
    2.  283 (BRIX Pro and NUC only) *
    3.  885
    4.  887
    5.  888
    6.  889
    7.  892
    8.  898
    9.  1150
    10. 1220

2.  Supported Audio IDs
    1. Audio ID: 1 - supports 269, 283, 885, 887, 888, 889, 892, 898, 1150
        Realtek ALC audio (default, 1/2/3/5/6 motherboard audio ports)
    2. Audio ID: 2 - supports 887, 888, 889, 892, 898, 1150
        Realtek ALC/5.1 surround sound (3 motherboard audio ports)
    3. Audio ID: 3 - supports 887, 888, 889, 892, 898
        HD3000/HD4000 HDMI audio with Realtek ALC audio

**D. More Information**

1. [Realtek ALC AppleHDA](https://github.com/toleda/audio_ALC_guides/blob/master/Realtek%20ALC%20AppleHDA.pdf)
    1. Installation
    2. Details/Support
    3. Troubleshooting
2. [Realtek ALC guides](https://github.com/toleda/audio_ALC_guides)
    1. Enhancemants
        1. Customization
        2. Surround Sound
    2. Troubleshooting
        1. No Audio Devices
        2. No Sound
        3. No Audio After Sleep/Wake
    3. Utilities
        1. Identify Audio Codec
        2. Restore native AppleHDA

**E. [Problem Reporting](https://github.com/toleda/audio_ALC_guides/blob/master/Problem%20Reporting.md)**

1. Problem Reporting/Post to
2. Problem Reporting/Attached requested files

Credit
THe KiNG, bcc9, RevoGirl, PikeRAlpha, SJ\_UnderWater, RehabMan, TimeWalker75a, lisai9093, [abxite](http://applelife.ru/threads/patchim-applehda-s-pomoschju-zagruzchika.39406/#post-353647)

toleda https://github.com/toleda/audio_cloverALC
