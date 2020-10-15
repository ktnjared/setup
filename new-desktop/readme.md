# New Desktop 2021

In 2020, I gave my Ryzen 1700X desktop to my brother-in-law when the desktop I built him with hand-me-down parts failed.

I've run with a 2019 MacBook Pro (16-inch) and a 2017 Dell XPS 13 Developer Edition with eGPUs. It's time to get back to
the desktop game.

## Purpose

* Daily Driver
  * [Windows 10](https://www.microsoft.com/en-us/software-download/windows10) Pro
  * [WSL](https://docs.microsoft.com/en-us/windows/wsl/) 2
    * [Ubuntu 20.04](https://www.microsoft.com/en-us/p/ubuntu-2004-lts/9n6svws3rx71)
* Development
  * [Python](https://www.python.org/)
    * [Visual Studio Code](https://code.visualstudio.com/) + WSL 2
  * [Swift](https://swift.org/)

    | Platform                                                                                                                                                                                                       | Type    | IDE                                                                                                               |
    | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------- | ----------------------------------------------------------------------------------------------------------------- |
    | [Windows](https://swift.org/blog/swift-on-windows/)                                                                                                                                                            | metal   | [Toolchain](https://swift.org/download/) + [Visual Studio 2019](https://visualstudio.microsoft.com/vs/community/) |
    | WSL 2<br>&nbsp;&nbsp;↳ Ubuntu Linux                                                                                                                                                                            | Hyper-V | [Toolchain](https://swift.org/download/) + [Visual Studio Code](https://code.visualstudio.com/)                   |
    | WSL 2<br>&nbsp;&nbsp;↳ [Accelerated KVM guests on WSL 2](https://boxofcables.dev/accelerated-kvm-guests-on-wsl-2/)<br>&nbsp;&nbsp;&nbsp;&nbsp;↳ [macOS-Simple-KVM](https://github.com/foxlet/macOS-Simple-KVM) | Hyper-V | Xcode                                                                                                             |

* Gaming (Windows)
  * [Final Fantasy XIV](https://www.finalfantasyxiv.com/)
  * [Minecraft](https://minecraft.net/)
* Streaming
  * [Twitch](https://twitch.tv/)
* Virtualization
  * [Hyper-V](https://docs.microsoft.com/en-us/virtualization/hyper-v-on-windows/)
  * KVM via WSL 2
    * monitor [github/microsoft/WSL/issues/4193/Nested Virtualization for WSL2 VM](https://github.com/microsoft/WSL/issues/4193)
      * currently works in Insiders Advanced *#2020-10-14; should be functional for 20H2 or 21H1 GA*
    * see ([Accelerated KVM guests on WSL 2](https://boxofcables.dev/accelerated-kvm-guests-on-wsl-2/) + [macOS-Simple-KVM](https://github.com/foxlet/macOS-Simple-KVM))
      * Yes, it's real. Video on Reddit:<br>
        [macOS on QEMU/KVM on WSL2 on Windows - it's virtual machines all the way down!](https://www.reddit.com/r/hackintosh/comments/h98cqx/macos_on_qemukvm_on_wsl2_on_windows_its_virtual/)
      * [MacOS on WSL2(Win10)](https://sugeul.github.io/2020-06-21-MacOS-on-WSL2/)

## Parts List

### Computer

| Part        | Cost<br>(MSRP$) | Manufacturer            | Model                                              |     Purchased      | Notes                                                                                                         |
| :---------- | --------------: | ----------------------- | -------------------------------------------------- | :----------------: | ------------------------------------------------------------------------------------------------------------- |
| **CPU**     |           `449` | [AMD][CPUman]           | [Ryzen 7 5800X][CPUmod]                            |        :x:         | 8 cores<br>16 thread<br>105W TDP                                                                              |
| **GPU**     |           `700` | [NVIDIA][GPUman]        | [GeForce RTX 3080][GPUmod]                         |        :x:         | Since this is *2021 Build*, am waiting to see Big Navi from AMD as well, but right now this is the selection. |
| **RAM**     |           `130` | [Corsair][RAMman]       | [CMK32GX4M2B3200C16<br>VENGEANCE LPX 32GB][RAMmod] |        :x:         | 32GB<br>(2x16GB)<br>DDR4<br>3200MHz<br>C16<br>Black                                                           |
| **SSD 0**   |           `760` | [Sabrent][SSD0man]      | [Rocket Q 4TB][SSD0mod]                            |        :x:         | NVMe<br>M.2 2280<br>PCIe Gen3 x4                                                                              |
| **SSD 1**   |             `-` | [Samsung][SSD1man]      | [512 GB PM981][SSD1mod]                            | :heavy_check_mark: | NVMe<br>M.2 2280                                                                                              |
| **MOBO**    |           `???` | [][MOBOman]             | [][MOBOmod]                                        |        :x:         | mITX                                                                                                          |
| **Case**    |           `210` | [FormD][CASEman]        | [T1 v1.1][CASEmod]                                 |        :x:         | white mITX case<br>9.5 Liters                                                                                 |
| **PSU**     |           `185` | [Corsair][PSUman]       | [SF750][PSUmod]                                    |        :x:         | SFX<br>750W<br>80+ Plat                                                                                       |
| **HSF**     |            `80` | [Cooler Master][HSFman] | [MasterLiquid ML240L V2][HSFmod]                   |        :x:         |                                                                                                               |
| **Fan**     |            `20` | [Noctua][FANman]        | [NF-A12x15 Chromax][FANmod]                        |        :x:         | 120x120x15<br>94.2 m³/h<br>1850 RPM<br>23.9 dB                                                                |
| **Fan**     |            `20` | [Noctua][FANman]        | [NF-A12x15 Chromax][FANmod]                        |        :x:         | 120x120x15<br>94.2 m³/h<br>1850 RPM<br>23.9 dB                                                                |
| ***TOTAL*** |    ***`2554`*** |                         |                                                    |                    | MSRP Prices.<br>Actual prices will be lower.                                                                  |

### External Components

| Part           | Cost<br>(MSRP$) | Manufacturer                        | Model                      |     Purchased      | Notes                                                                                 |
| :------------- | --------------: | ----------------------------------- | -------------------------- | :----------------: | ------------------------------------------------------------------------------------- |
| **Display**    |           `800` | [LG][Displayman]                    | [27GN950-B][Displaymod]    |        :x:         | 27"<br>4K UHD<br>IPS<br>HDR 600<br>144Hz / 1ms<br>G-SYNC<br>AMD FreeSync Pro<br>USB-C |
| **Headphones** |           `???` | ???[][Headphonesman]                | ???[][Headphonesmod]       | :heavy_check_mark: |                                                                                       |
| **Keyboard 1** |           `???` | [ZSA Technology Labs][ergodoxman] | [ErgoDox EZ][ergodoxmod] | :heavy_check_mark: |                                                                                       |
| **Keyboard 0** |           `???` | [Logitch][Keyboard1man]             | [ERGO K860][Keyboard1mod]  | :heavy_check_mark: | For when I need ergonomics, but QWERTY layout with short-throw switches.              |
| **Keyboard 2** |           `???` | ???[][Keyboard2man]                 | ???[][Keyboard2mod]        | :heavy_check_mark: |                                                                                       |
| **Mouse**      |           `???` | ???[][Mouseman]                     | ???[][Mousemod]            | :heavy_check_mark: |                                                                                       |
| ***TOTAL***    |     ***`800`*** |                                     |                            |                    | MSRP Prices.<br>Actual prices will be lower.                                          |

## Resources

* [/r/FormD][reddit1]
* [FormD T1 AIO Compatibility List][gdocs1]
* [Optimum Tech — 1 — FormD T1 Review][youtube1]
* [Optimum Tech — 2 — FormD T1 Custom Loop Build][youtube2]
* [Optimum Tech — 3 — Fixing fittings + thermal testing][youtube3]
* [Optimum Tech — 4 — FormD T1 RTX 3090/3080][youtube4]

<!-- URLs PARTS -->
[CASEman]: https://formdworks.com/ "FormD"
[CASEmod]: https://formdworks.com/products/t1 "T1"
[CPUman]: https://www.amd.com/ "AMD"
[CPUmod]: https://www.amd.com/en/products/cpu/amd-ryzen-7-5800x "AMD Ryzen 7 5800X"
[Displayman]: https://www.lg.com/ ""
[Displaymod]: https://www.lg.com/us/monitors/lg-27gn950-b-gaming-monitor "LG 27GN950-B 27 inch UltraGear 4K Nano IPS 1ms G-SYNC Compatible Gaming Monitor"
[FANman]: https://www.noctua.at/ "Noctua.at"
[FANmod]: https://noctua.at/en/nf-a12x15-pwm-chromax-black-swap "NF-A12x15 PWM chromax.black.swap"
[GPUman]: https://www.nvidia.com/ "NVIDIA"
[GPUmod]: https://www.nvidia.com/en-us/geforce/graphics-cards/30-series/rtx-3080/ "GeForce RTX 3080 Graphics Card | NVIDIA"
[Headphonesman]:  ""
[Headphonesmod]:  ""
[HSFman]: https://www.coolermaster.com/ "Cooler Master"
[HSFmod]: https://www.coolermaster.com/catalog/coolers/cpu-liquid-coolers/masterliquid-ml240l-v2-rgb/ "MASTERLIQUID ML240L V2 RGB"
[ergodoxman]: https://blog.zsa.io/ "The Ergo"
[ergodoxmod]: https://ergodox-ez.com/ "ErgoDox EZ: An Incredible Mechanical Ergonomic Keyboard"
[Keyboard1man]: https://www.logitech.com/ "Logitech"
[Keyboard1mod]: https://www.logitech.com/en-us/products/keyboards/k860-split-ergonomic.920-009166.html "ERGO K860"
[Keyboard2man]:  ""
[Keyboard3mod]:  ""
[MOBOman]:  ""
[MOBOmod]:  ""
[Mouseman]:  ""
[Mousemod]:  ""
[PSUman]: https://www.corsair.com/ "CORSAIR"
[PSUmod]: https://www.corsair.com/us/en/Categories/Products/Power-Supply-Units/Power-Supply-Units-Advanced/SF-Series/p/CP-9020186-NA "SF Series SF750"
[RAMman]: https://www.corsair.com/ "Corsair"
[RAMmod]: https://www.corsair.com/us/en/Categories/Products/Memory/VENGEANCE-LPX/p/CMK32GX4M2B3200C16 "Vengeance LPX 32GB (2x16GB) 3200MHz C16 DDR4 DRAM Memory Kit – Black"
[SSD0man]: Sabrent "https://www.sabrent.com/"
[SSD0mod]: https://www.sabrent.com/product/SB-RKTQ-4TB/rocket-q-4tb-nvme-pcie-m-2-2280-internal-ssd-high-performance-solid-state-drive/ "Rocket Q 4TB NVMe PCIe M.2 2280 Internal SSD Solid State Drive (SB-RKTQ-4TB)"
[SSD1man]: https://www.samsung.com/semiconductor/ "Samsung Semiconductor Global Website"
[SSD1mod]: https://www.samsung.com/semiconductor/ssd/client-ssd/MZVLB512HAJQ/ "PM981 MZVLB512HAJQ | Samsung Semiconductor Global Website"

<!-- URLs OTHER -->
[gdocs1]: https://docs.google.com/spreadsheets/d/12fTWe4Y4prgAHPhsk4HA2-wK8PRnPyy2ZxIzcbNapNE/edit?usp=sharing "Google Sheets — FormD T1 AIO Compatibility List"
[reddit1]: https://www.reddit.com/r/FormD/ "/r/FormD"
[youtube1]: https://youtu.be/Ou4iWsBNSmY "YouTube — Optimum Tech — FormD T1 - The Ultimate Sub-10L Case!"
[youtube2]: https://youtu.be/W1mO5dNJIgo "YouTube — Optimum Tech — SFF Endgame - Mini Liquid Cooled i9 / 2080 Ti Build"
[youtube3]: https://youtu.be/dbLugatTfTc "YouTube — Optimum Tech — The Liquid Cooled T1 Build is Complete!"
[youtube4]: https://youtu.be/_GhFSSLp-mE "YouTube — Optimum Tech — This Wasn’t Supposed to Work – RTX 3090 / 3080 in Sub-10L."
