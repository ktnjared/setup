# New Desktop 2021

In 2020, I gave my Ryzen 1700X desktop to my brother-in-law when the desktop I built him with hand-me-down parts failed.

## Current Setup

1. 2017 Dell XPS 13 Developer Edition
    - Dual Boot
        - Ubuntu Linux 20.04
        - Windows 10 Pro
    - 1 TB NVMe
    - 16 GB RAM
    - Intel UHD 630 iGPU
2. 2018 Mac mini
  * Dual Boot
    * macOS 11.0 Big Sur developer beta 10
    * Windows 10 Pro (Boot Camp)
  * 512 GB NVMe
  * 8 GB RAM
  * Intel UHD 630 iGPU
3. 2019 MacBook Pro (16-inch)
  * Dual Boot
    * macOS 11.0 Big Sur developer beta 10
    * macOS 10.15.7 Catalina
    * Windows 10 Pro (Boot Camp)
  * 512 GB NVMe
  * 16 GB RAM
  * Intel UHD 630 iGPU
  * AMD Radeon Pro 5300M

All 3 machines are equipped with Thunderbolt 3 and thus have available to them

* Razer Core X with an NVIDIA GeForce GTX 1080 Founders Edition GPU
* Razer Core X with a PowerColor Radeon RX 5700XT Founders Edition GPU

It's time to get back to the desktop game.

## Purpose

* Daily Driver
  * [Windows 10][os_win10] Pro
  * [WSL][wsl] 2
    * [Ubuntu 20.04][os_ubuntu_wsl]
    * [macOS][os_macos]
      * [Hayden Barnes][hayden]: [Accelerated KVM guests on WSL 2](https://boxofcables.dev/accelerated-kvm-guests-on-wsl-2/)
      * [Foxlet][foxlet]: [macOS-Simple-KVM](https://github.com/foxlet/macOS-Simple-KVM)
      * [u/my_spaghetti][u_my_spaghetti] on [r/hackintosh][r_hackintosh]: [macOS on QEMU/KVM on WSL2 on Windows - it's virtual machines all the way down!][reddit1]
      * [Sugeul Jin][segeul]: [MacOS on WSL2(Win10)](https://sugeul.github.io/2020-06-21-MacOS-on-WSL2/)
* Development
  * [Python](https://www.python.org/)
    * [Visual Studio Code][vscode]
    * WSL 2
  * [Swift](https://swift.org/)

    | Platform             | IDE                                                                                                         |
    | -------------------- | ----------------------------------------------------------------------------------------------------------- |
    | [Windows][swift_win] | [Swift Toolchain][swift_toolchain] + [Visual Studio 2019](https://visualstudio.microsoft.com/vs/community/) |
    | WSL 2: macOS         | [Xcode][xcode] + [Swift Playgrounds][swift_playgrounds]                                                     |
    | WSL 2: Ubuntu Linux  | [Swift Toolchain][swift_toolchain] + [Visual Studio Code][vscode]                                           |

* Gaming (Windows)
  * [Battle.net](https://www.blizzard.com/en-us/apps/battle.net/desktop)
    * [StarCraft](https://starcraft.com/) Remastered
    * [StarCraft 2](https://starcraft2.com/)
    * [World of Warcraft](https://worldofwarcraft.com/)
  * [Final Fantasy XIV](https://www.finalfantasyxiv.com/)
  * [Microsoft Game Pass Ultimate](https://www.xbox.com/xbox-game-pass/pc-games)
    * [Forza Horizon 4](https://forzamotorsport.net/games/fh4)
    * [Microsoft Flight Simulator](https://www.xbox.com/games/microsoft-flight-simulator)
    * [Minecraft for Windows 10](https://www.minecraft.net/store/minecraft-windows10) (Bedrock Edition)
  * [Minecraft](https://minecraft.net/) (Java Edition)
* Streaming
  * [Twitch](https://twitch.tv/)
* Virtualization
  * [Hyper-V](https://docs.microsoft.com/virtualization/hyper-v-on-windows/)
  * [KVM](https://www.linux-kvm.org/page/Main_Page) via WSL 2 (aka "nested virtualization")
    * monitor [github/microsoft/WSL/issues/4193/Nested Virtualization for WSL2 VM](https://github.com/microsoft/WSL/issues/4193)
      * As of 2020-10-14, works in Insiders Advanced
      * should be functional for 20H2 or 21H1 GA 🤞🏻

## Thoughts

* GPU
  * Since this is *"2021 Build"*, am waiting to see Big Navi from AMD as well, but right now the RTX is the selection.
  * Requirement: Full-size DisplayPort output for VGA output device to CRT displays when feeling cheeky
* Monitor Discussion
  * There does not seem to be a monitor in existence yet that meets the wants that I have.
  * The [LG 27GN950-B][monitor] seems to be the closest for a non-curved display that would provide work + games. Re-evaluate closer to time of purchase.

      | Spec                          | Desired                                              | [LG 27GN950-B][monitor] | Meets   |
      | ----------------------------- | ---------------------------------------------------- | ----------------------- | ------- |
      | Display Size                  | 32"                                                  | 27"                     | :x:     |
      | Aspect Ratio                  | 3:2<br>16:10                                         | 16:9                    | :x:     |
      | Resolution                    | 4500x3000 [if 3:2]<br>3840x2400 (4K UHD+) [if 16:10] | 4K UHD (3840x2160)      | :x:     |
      | Panel Type                    | IPS                                                  | IPS                     | :smile: |
      | HDR                           | HDR10                                                | HDR 600                 | :x:     |
      | Refresh                       | 120 Hz or greater                                    | 144 Hz                  | :smile: |
      | Response                      | Under 5 ms                                           | 1 ms                    | :smile: |
      | Variable Refresh              | G-SYNC + FreeSync                                    | G-SYNC + FreeSync       | :smile: |
      | USB-C 3.1+ / USB 4            | Yes / Yes                                            | Yes / No                | :smile: |
      | Thunderbolt 3 / Thunderbolt 4 | Yes                                                  | No                      | :x:     |

  * My current [Samsung C27HG7x][monitor_current] will serve as a secondary display when necessary.

## Parts List

### Computer

#### Enclosure & Cooling

| Type     | Cost<br>(MSRP$) | Purchased | Part                                        | Details                                        |
| :------- | --------------: | :-------: | ------------------------------------------- | ---------------------------------------------- |
| **Case** |           `210` |    :x:    | [FormD T1 v1.1][case]                       | white mITX case<br>9.5 Liters                  |
| **HSF**  |            `80` |    :x:    | [Cooler Master MasterLiquid ML240L V2][hsf] |                                                |
| **Fan**  |            `20` |    :x:    | [Noctua NF-A12x15 Chromax][fan]             | 120x120x15<br>94.2 m³/h<br>1850 RPM<br>23.9 dB |
| **Fan**  |            `20` |    :x:    | [Noctua NF-A12x15 Chromax][fan]             | 120x120x15<br>94.2 m³/h<br>1850 RPM<br>23.9 dB |

#### Components

| Type         | Cost<br>(MSRP$) |     Purchased      | Part                                                 | Details                                     |
| :----------- | --------------: | :----------------: | ---------------------------------------------------- | ------------------------------------------- |
| **CPU**      |           `449` |        :x:         | [AMD Ryzen 7 5800X][cpu]                             | 8 cores<br>16 thread<br>105W TDP            |
| **GPU0**     |           `700` |        :x:         | [NVIDIA GeForce RTX 3080][gpu0]                      |                                             |
| **RAM**      |           `130` |        :x:         | [Corsair CMK32GX4M2B3200C16 VENGEANCE LPX 32GB][ram] | 2 x 16GB<br>DDR4<br>3200MHz<br>C16<br>Black |
| **Storage0** |           `760` |        :x:         | [Sabrent Rocket Q 4TB][storage0]                     | NVMe<br>M.2 2280<br>PGen3 x4                |
| **Storage1** |             `-` | :heavy_check_mark: | [Samsung 512 GB PM981][storage1]                     | NVMe<br>M.2 2280                            |
| **MOBO**     |             `?` |        :x:         | [?][motherboard]                                     | mITX<br>B550?                               |
| **PSU**      |           `185` |        :x:         | [Corsair SF750][psu]                                 | SFX<br>750W<br>80+ Plat                     |

#### Devices

##### Audio/Visual

| Type           | Cost<br>(MSRP$) |     Purchased      | Part                                    | Details |
| :------------- | --------------: | :----------------: | --------------------------------------- | ------- |
| **Monitor**    |           `800` |        :x:         | [LG 27GN950-B][monitor]                 |         |
| **Headphones** |             `-` | :heavy_check_mark: | [see headphones.md][gist_headphones]    |         |
| **Headset**    |             `-` | :heavy_check_mark: | [see headphones.md][gist_headphones]    |         |
| **Speakers**   |             `-` | :heavy_check_mark: | [Bose Companion 2 Series III][speakers] |         |


##### Input/Output

| Type               | Cost<br>(MSRP$) |     Purchased      | Part                                                                   | Details                                                           |
| :----------------- | --------------: | :----------------: | ---------------------------------------------------------------------- | ----------------------------------------------------------------- |
| **Keyboard**       |             `-` | :heavy_check_mark: | [Apple Magic Keyboard 2 with Numeric Keypad — Japanese][kbd_magic2jis] | QWERTY-based [JIS][jisjim] X 6002:1980<br>scissor switches        |
| **Keyboard**       |             `-` | :heavy_check_mark: | [Apple Magic Keyboard 2 with Numeric Keypad - English][kbd_magic2eng]  |
| **Keyboard**       |             `-` | :heavy_check_mark: | [CODE 104-key keyboard][kbd_code]                                      | 104-key US ASCII<br>Cherry MX Clear switches                      |
| **Keyboard**       |             `-` | :heavy_check_mark: | [Filco Majestouch 2 Ninja TKL][kbd_filco]                              | 87-key US ASCII<br>Cherry MX Brown switches                       |
| **Keyboard**       |             `-` | :heavy_check_mark: | [IBM Model F "XT"][kbd_modelf]                                         | QWERTY<br>buckling spring over a capacitive PCB                   |
| **Keyboard**       |             `-` | :heavy_check_mark: | [KBC Poker][kbd_poker2]                                                | 60% ANSI<br>Cherry MX Red switches                                |
| **Keyboard**       |             `-` | :heavy_check_mark: | [Logitch ERGO K860][kbd_logik860]                                      | QWERTY ergonomic<br>scissor switches                              |
| **Keyboard**       |             `-` | :heavy_check_mark: | [ZSA Technology Labs ErgoDox][kbd_ergodox]                             | Programmable, ortholinear layout<br>Kaihl Silent Box Red switches |
| **Mouse**          |             `-` | :heavy_check_mark: | [Logitech MX Master 2s Flow][mouse_logimxmaster2]                      |                                                                   |
| **Mouse**          |             `-` | :heavy_check_mark: | [Razer Naga Trinity][mouse_razernaga3]                                 |                                                                   |
| **Keyboard/Mouse** |             `-` | :heavy_check_mark: | [Razer Turret for Xbox One][kbd_razerturretxboxone]                    |                                                                   |
| **Trackpad**       |             `?` |        :x:         | ?                                                                      |                                                                   |

## Resources

* [/r/FormD][reddit1]
* [FormD T1 AIO Compatibility List][gdocs1]
* [Optimum Tech — 1 — FormD T1 Review][youtube1]
* [Optimum Tech — 2 — FormD T1 Custom Loop Build][youtube2]
* [Optimum Tech — 3 — Fixing fittings + thermal testing][youtube3]
* [Optimum Tech — 4 — FormD T1 RTX 3090/3080][youtube4]

<!-- URLS - PARTS -->
[case]: https://formdworks.com/products/t1 "T1"
[cpu]: https://www.amd.com/en/products/cpu/amd-ryzen-7-5800x "AMD Ryzen 7 5800X"
[fan]: https://noctua.at/en/nf-a12x15-pwm-chromax-black-swap "NF-A12x15 PWM chromax.black.swap"
[gist_headphones]: https://gist.github.com/ktnjared/218caae44537167bc72445856c6db65e
[gpu0]: https://www.nvidia.com/en-us/geforce/graphics-cards/30-series/rtx-3080/ "GeForce RTX 3080 Graphics Card | NVIDIA"
[hsf]: https://www.coolermaster.com/catalog/coolers/cpu-liquid-coolers/masterliquid-ml240l-v2-rgb/ "MASTERLIQUID ML240L V2 RGB"
[kbd_code]: https://codekeyboards.com/
[kbd_ergodox]: https://ergodox-ez.com/ "ErgoDox EZ: An Incredible Mechanical Ergonomic Keyboard"
[kbd_filco]: https://deskthority.net/wiki/Filco_Majestouch
[kbd_logik860]: https://www.logitech.com/en-us/products/keyboards/k860-split-ergonomic.920-009166.html "ERGO K860"
[kbd_magic2eng]: https://www.apple.com/shop/product/MQ052LL/A/magic-keyboard-with-numeric-keypad-us-english-silver
[kbd_magic2jis]: https://www.apple.com/shop/product/MQ052J/A/magic-keyboard-with-numeric-keypad-japanese-silver
[kbd_modelf]: https://deskthority.net/wiki/IBM_Personal_Computer_keyboard
[kbd_poker2]: https://deskthority.net/wiki/KBC_Poker
[kbd_razerturretxboxone]: https://www.razer.com/gaming-keyboards/razer-turret-for-xbox-one/RZ84-02820200-B3U1
[monitor_current]: https://www.samsung.com/us/computing/monitors/gaming/27--chg70-gaming-monitor-with-quantum-dot-lc27hg70qqnxza/
[monitor]: https://www.lg.com/us/monitors/lg-27gn950-b-gaming-monitor "LG 27GN950-B 27 inch UltraGear 4K Nano IPS 1ms G-SYNC Compatible Gaming Monitor"
[mouse_logimxmaster2]: https://www.logitech.com/en-ph/product/mx-master-2s-flow
[mouse_razernaga3]: https://www.razer.com/gaming-mice/razer-naga-trinity/RZ01-02410100-R3U1
[psu]: https://www.corsair.com/us/en/Categories/Products/Power-Supply-Units/Power-Supply-Units-Advanced/SF-Series/p/CP-9020186-NA "SF Series SF750"
[ram]: https://www.corsair.com/us/en/Categories/Products/Memory/VENGEANCE-LPX/p/CMK32GX4M2B3200C16 "Vengeance LPX 32GB (2x16GB) 3200MHz C16 DDR4 DRAM Memory Kit – Black"
[speakers]: https://www.bose.com/en_us/products/speakers/stereo_speakers/companion-2-series-iii-multimedia-speaker-system.html
[storage0]: https://www.sabrent.com/product/SB-RKTQ-4TB/rocket-q-4tb-nvme-pcie-m-2-2280-internal-ssd-high-performance-solid-state-drive/ "Rocket Q 4TB NVMe PCIe M.2 2280 Internal SSD Solid State Drive (SB-RKTQ-4TB)"
[storage1]: https://www.samsung.com/semiconductor/ssd/client-ssd/MZVLB512HAJQ/ "PM981 MZVLB512HAJQ | Samsung Semiconductor Global Website"

<!-- URLs OTHER -->
[foxlet]: https://foxlet.furcode.co/
[gdocs1]: https://docs.google.com/spreadsheets/d/12fTWe4Y4prgAHPhsk4HA2-wK8PRnPyy2ZxIzcbNapNE/edit?usp=sharing "Google Sheets — FormD T1 AIO Compatibility List"
[hayden]: https://twitter.com/unixterminal
[jisjim]: https://en.wikipedia.org/wiki/Japanese_input_method
[r_hackintosh]: https://www.reddit.com/r/hackintosh/
[reddit1]: https://www.reddit.com/r/FormD/ "/r/FormD"
[segeul]: https://sugeul.github.io/
[swift_playgrounds]: https://www.apple.com/swift/playgrounds/
[swift_toolchain]: https://swift.org/download/
[u_my_spaghetti]: https://www.reddit.com/user/my_spaghetti/
[reddit1]: https://www.reddit.com/r/hackintosh/comments/h98cqx/macos_on_qemukvm_on_wsl2_on_windows_its_virtual/
[xcode]: https://developer.apple.com/xcode/
[youtube1]: https://youtu.be/Ou4iWsBNSmY "YouTube — Optimum Tech — FormD T1 - The Ultimate Sub-10L Case!"
[youtube2]: https://youtu.be/W1mO5dNJIgo "YouTube — Optimum Tech — SFF Endgame - Mini Liquid Cooled i9 / 2080 Ti Build"
[youtube3]: https://youtu.be/dbLugatTfTc "YouTube — Optimum Tech — The Liquid Cooled T1 Build is Complete!"
[youtube4]: https://youtu.be/_GhFSSLp-mE "YouTube — Optimum Tech — This Wasn’t Supposed to Work – RTX 3090 / 3080 in Sub-10L."
[os_win10]: https://www.microsoft.com/en-us/software-download/windows10
[wsl]: https://docs.microsoft.com/en-us/windows/wsl/
[os_macos]: https://apple.com/macos/
[swift_win]: https://swift.org/blog/swift-on-windows/
[os_ubuntu_wsl]: https://ubuntu.com/wsl
[vscode]: (https://code.visualstudio.com/