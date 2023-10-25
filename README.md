# [Releases and Downloads](https://github.com/RE3CON/uv-k5-firmware-fagci-mod/releases)<br/>
[Latest Source](https://github.com/RE3CON/uv-k5-firmware-fagci-mod/archive/refs/heads/main.zip)

# Instructions PDF English:
[fagci_specrum_help_20231010-0735 en.pdf](http://quansheng.v6.navy/docs/fagci_specrum_help_20231010-0735%20en.pdf)
<br/><br/>
[QuanSheng.UV.K5.Spectrum.analyzer.guide.EN.pdf](http://quansheng.v6.navy/docs/QuanSheng.UV.K5.Spectrum.analyzer.guide.EN.pdf) 
<hr/>

TX:

<a href="/docs/img/display6.jpg"><img src="/docs/img/display6m.jpg" /></a>

## Features:
- Spectrum Analyzer + Scan: F + 5 (NOAA feature), etc...
- TX/RX Freq Ranges full 15 MHz - 2 GHz
- RX Modulation:
FM, WFM, AM, SSB, RAW
- 2 different Tone Burst:
- Repeater default Tone 1750 Hz: Sidekey F2 + PTT
- NOAA Tone-Squelch 1050 Hz: Sidekey S1
- ...and much more...

RX:

<a href="/docs/img/display3.jpg"><img src="/docs/img/display3m.jpg" /></a>

# Open reimplementation of the Quan Sheng UV K5 v2.1.27 firmware

This repository is a preservation project of the UV K5 v2.1.27 firmware.
It is dedicated to understanding how the radio works and help developers making their own customisations/fixes/etc.
It is by no means fully understood or has all variables/functions properly named, as this is best effort only.
As a result, this repository will not include any customisations or improvements over the original firmware.

You can find an alternate branch called "fixes" that contains fixes for real bugs present in the original firmware.
This branch will also accumulate fixes/improvements from newer releases by QS (for example v2.01.31).

For improved/better firmware and new features, you can find the following repositories by other collaborators:

* [https://github.com/fagci/uv-k5-firmware-fagci-mod](https://github.com/fagci/uv-k5-firmware-fagci-mod)
* [https://github.com/OneOfEleven/uv-k5-firmware-custom](https://github.com/OneOfEleven/uv-k5-firmware-custom)
* [https://github.com/Tunas1337/uv-k5-firmware](https://github.com/Tunas1337/uv-k5-firmware) (Check the branches)
* [https://github.com/rebezhir/openquack](https://github.com/rebezhir/openquack) for Russian Lang. speaking users

# Makefile Feature Settings
Edit Makefile before building the F/W

- 1 = enable
- 2 = disable
<pre>
ENABLE_AIRCOPY := 0
ENABLE_ALARM := 0
ENABLE_AM_FIX := 1
ENABLE_FMRADIO := 0
ENABLE_NOAA := 0
ENABLE_OVERLAY := 0
ENABLE_SPECTRUM := 1
ENABLE_SWD := 1
ENABLE_TX1750 := 1
ENABLE_UART := 1
ENABLE_NOSCANTIMEOUT := 1
ENABLE_KEEPNAMEONSAVE := 1
ENABLE_RSSIBAR := 1
ENABLE_ALL_REGISTERS := 1
ENABLE_FASTER_CHANNEL_SCAN := 1
ENABLE_UART_CAT := 1

SPECTRUM_AUTOMATIC_SQUELCH := 1
SPECTRUM_EXTRA_VALUES := 1
</pre>

# Compiler

arm-none-eabi GCC version 10.3.1 is recommended, which is the current version on Ubuntu 22.04.03 LTS.
Other versions may generate a flash file that is too big with >60kb.
You can get an appropriate version from: [https://developer.arm.com/downloads/-/gnu-rm](https://developer.arm.com/downloads/-/gnu-rm)

# Building

To build the firmware, you need to fetch the submodules and then run make:
```
git submodule update --init --recursive --depth=1
make
```

# Flashing with the official updater

* Use the firmware.packed.bin file

# Flashing with [k5prog](https://github.com/piotr022/k5prog)

* ./k5prog -F -YYY -b firmware.bin

# Flashing with SWD

* If you own a JLink or compatible device and want to use the Segger software, you can find a flash loader [here](https://github.com/DualTachyon/dp32g030-flash-loader)
* If you want to use OpenOCD instead, you can use run "make flash" off this repo.
* The DP32G030 has flash masking to move the bootloader out of the way. Do not try to flash your own way outside of the above methods or risk losing your bootloader.

# Support

* If you like my work, you can support me through https://ko-fi.com/DualTachyon

# Credits

Many thanks to various people on Telegram for putting up with me during this effort and helping:

* [Mikhail](https://github.com/fagci/)
* [Andrej](https://github.com/Tunas1337)
* [Manuel](https://github.com/manujedi)
* @wagner
* @Lohtse Shar
* [@Matoz](https://github.com/spm81)
* @Davide
* @Ismo OH2FTG
* [OneOfEleven](https://github.com/OneOfEleven)
* and others I forget

# License

Copyright 2023 Dual Tachyon
[https://github.com/DualTachyon](https://github.com/DualTachyon)

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.

