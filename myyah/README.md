# 

## Windows 10

1. Install the latest version of [Windows 10](https://www.microsoft.com/en-us/software-download/windows10).
    - Local user
    - Privacy Settings page
        
        | Option             | on/off | Option               | on/off |
        | ------------------ | ------ | -------------------- | ------ |
        | Speech recognition | off    | Location             | on     |
        | Diagnostics        | on     | Tailored experiences | off    |
        | Relevant Ads       | off    |                      |        |
    - Cortana off
    - 

2. Install all updates from Software Update.
    - Continue to Check for Updates, reboot, and rerun until there are none left
3. Install [Dell SupportAssist](https://downloads.dell.com/serviceability/catalog/SupportAssistInstaller.exe).
4. Run all steps.

## [Windows Subsystem for Linux](https://docs.microsoft.com/en-us/windows/wsl/) (WSL)

Installation documentation is [available in Microsoft Docs](https://docs.microsoft.com/en-us/windows/wsl/install-win10).

1. Enable WSL

    Open PowerShell as Administrator and run

    ```shell
    dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
    ```

2. Enable Virtual Machine Platform

    ```shell
    dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
    ```

3. Reboot.
4. Install the [WSL2 Linux Kernel update package for x64 machines](https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi).
5. Set WSL 2 a the default version

    ```shell
    wsl --set-default-version 2
    ```

6. Install a Linux distribution via the [Microsoft Store](https://aka.ms/wslstore).
    - [Kali Linux](https://www.microsoft.com/store/apps/9PKR34TNCV07)
    - [Pengwin](https://www.microsoft.com/store/apps/9NV1GV1PXZ6P)
    - [Ubuntu 20.04 LTS](https://www.microsoft.com/store/apps/9n6svws3rx71)
7. Launch the distribution to initiate setup. 

## Microsoft Store

### Software 

- [Bitwarden](https://www.microsoft.com/store/productId/9PJSDV0VPK04)
- [EarTrumpet](https://www.microsoft.com/store/productId/9NBLGGH516XP)
- [Intel Graphics Command Center](https://www.microsoft.com/store/productId/9PLFNLNT3G5G)
- [Krita](https://www.microsoft.com/store/productId/9N6X57ZGRW96)
- [Microsoft Remote Desktop](https://www.microsoft.com/store/productId/9WZDNCRFJ3PS)
- [Microsoft To Do](https://www.microsoft.com/store/productId/9NBLGGH5R558)
- [Monitorian](https://www.microsoft.com/store/productId/9NW33J738BL0)
- [NVIDIA Control Panel](https://www.microsoft.com/store/productId/9NF8H0H7WMLT)
- [QuickLook](https://www.microsoft.com/store/productId/9NV4BS3L1H4S)
- [Windows Terminal](https://www.microsoft.com/store/productId/9N0DX20HK701)
- [X410](https://www.microsoft.com/store/productId/9NLP712ZMN9Q)
- [Xbox](https://www.microsoft.com/store/productId/9MV0B5HZVK9Z)
- [Xbox Accessories](https://www.microsoft.com/store/productId/9NBLGGH30XJ3)
- [Xbox Console Companion](https://www.microsoft.com/store/productId/9WZDNCRFJBD8)
- [Xbox Dev Mode Companion](https://www.microsoft.com/store/productId/9NBLGGH519CP)
- [Xbox Insider Hub](https://www.microsoft.com/store/productId/9NBLGGH68VSK)

#### Games

- [Forza Horizon 4](https://www.microsoft.com/store/productId/9PNQKHFLD2WQ)
    - all content included in the [Forza Horizon 4 Ultimate Add-Ons Bundle](https://www.microsoft.com/store/productId/9PNQKHFLD2WQ)
- [Minecraft for Windows 10](https://www.microsoft.com/store/productId/9NBLGGH2JHXJ)
- [Phantasy Star 2 Online](https://www.microsoft.com/store/productId/9P1RSQ5MGPCR)

#### Extensions

- [AV1 Video Extension](https://www.microsoft.com/store/productId/9MVZQVXJBQ9V)
- [HEIF Image Extensions](https://www.microsoft.com/store/productId/9PMMSR1CGPWG)
- [HEVC Video Extensions](https://www.microsoft.com/store/productId/9NMZLZ57R3T7)
- [MPEG-2 Video Extension](https://www.microsoft.com/store/productId/9N95Q1ZZPMH4)
- [Raw Image Extension](https://www.microsoft.com/store/productId/9NCTDW2W1BH8)
- [VP9 Video Extensions](https://www.microsoft.com/store/productId/9N4D0MSMP0PT)
- [Web Media Extensions](https://www.microsoft.com/store/productId/9N5TDP8VCMHS)
- [Webp Image Extensions](https://www.microsoft.com/store/productId/9PG2DK419DRG)

## [WinGet](https://github.com/microsoft/winget-cli)

- TODO once out of Insiders-only release.

## [`scoop`](https://scoop.sh/)

Scoop is a software manager that installs things into your user directory, so you don't need Administrative permissions to install it.

1. Install the latest version of [PowerShell](https://github.com/PowerShell/PowerShell/releases).
2. Install Scoop.

    ```shell
    Invoke-Expression (New-Object System.Net.WebClient).DownloadString('https://get.scoop.sh')
    ```
3. Set the `ExecutionPolicy` for current user to allow `RemoteSigned`.

    ```shell
    Set-ExecutionPolicy RemoteSigned -scope CurrentUser
    ```

### Prerequisites for Scoop-installed Software

- Install the [latest .Net Core Runtime](https://dotnet.microsoft.com/download/dotnet-core/current/runtime).
    - This is required for [PowerToys](https://github.com/microsoft/PowerToys).
    - Once WinGet is available, this will not be required as PowerToys will be installed [using WinGet](https://github.com/microsoft/PowerToys#via-winget-preview), which will pull the required .Net Runtime.
- Add `nonportable` bucket to Scoop

    ```shell
    scoop bucket add nonportable
    ```

### Programs

- [Discord](https://discord.com/) [for Windows](https://discord.com/api/download?platform=win)
- [git](https://git-scm.com/) [for Windows](https://gitforwindows.org/)
- [neofetch](https://github.com/dylanaraps/neofetch)
- [PowerToys](https://github.com/microsoft/PowerToys)
    - [ ] TODO: move to intalling via WinGet when available
- [Python](https://www.python.org/) [3.8.x for Windows](https://www.python.org/downloads/)
- [Signal](https://signal.org/) [for Desktop](https://signal.org/download/)
- [Speccy](https://www.ccleaner.com/speccy)
- [Telegram](https://telegram.org/) [Desktop](https://desktop.telegram.org/)
- [Windows 10 Auto Dark Mode](https://github.com/Armin2208/Windows-Auto-Night-Mode)
    - [ ] TODO: move to intalling via WinGet when available

## Manually Downloaded Installers

- [GitHub](https://github.com/) [Desktop](https://desktop.github.com/) [client](https://central.github.com/deployments/desktop/desktop/latest/win32)
- [Visual Studio Code](https://code.visualstudio.com/)

## Games

- [Battle.net](https://www.blizzard.com/en-us/) [Desktop client](https://www.blizzard.com/apps/battle.net/desktop)
    - Install Heroes of the Storm
    - Install Overwatch
    - Install World of Warcraft
    - Install World of Warcraft Classic
    - [Twitch](https://twitch.tv/) [App for Windows](https://desktop.twitchsvc.net/installer/windows/TwitchSetup.exe) for Warcraft Mods
        - [AdiBags](https://www.curseforge.com/wow/addons/adibags)
        - [AnyFont](https://www.curseforge.com/wow/addons/anyfont)
        - [AutoVendor](https://www.curseforge.com/wow/addons/autovendor)
        - [GatherMate2](https://www.curseforge.com/wow/addons/gathermate2)
        - [GatherMate2_Data](https://www.curseforge.com/wow/addons/gathermate2_data)
        - [Gnosis (Castbars and Timers)](https://www.curseforge.com/wow/addons/gnosis)
        - [HandyNotes](https://www.curseforge.com/wow/addons/handynotes)
        - [KuiNameplates](https://www.curseforge.com/wow/addons/kuinameplates)
        - [MapCoords](https://www.curseforge.com/wow/addons/map-coords)
        - [MBB](https://www.curseforge.com/wow/addons/mbb)
        - [Pawn](https://www.curseforge.com/wow/addons/pawn)
        - [Shadowed Unit Frames](https://www.curseforge.com/wow/addons/shadowed-unit-frames)
- [Epic Games Store](https://www.epicgames.com/store/) [client](https://launcher-public-service-prod06.ol.epicgames.com/launcher/api/installer/download/EpicGamesLauncherInstaller.msi)
- [Final Fantasy XIV](https://na.finalfantasyxiv.com/) [North American game client](http://gdl.square-enix.com/ffxiv/inst/ffxivsetup.exe)
    - [Menolly Caryatid](https://na.finalfantasyxiv.com/lodestone/character/21378972/) on [Famfrit (Primal)](https://na.finalfantasyxiv.com/lodestone/worldstatus/)
- [Genshin Impact](https://genshin.mihoyo.com/) [client](https://ys-api-os.mihoyo.com/event/download_porter/link/ys_global/genshinimpactpc/default)
- [GOG](https://www.gog.com/) [Galaxy client](https://www.gog.com/galaxy)
- [Minecraft](https://www.minecraft.net/) [Java Edition client](https://www.minecraft.net/en-us/download)
- [Steam](https://store.steampowered.com/) [client](https://cdn.cloudflare.steamstatic.com/client/installer/SteamSetup.exe)

## PowerShell

```shell
Install-Module posh-git -Scope CurrentUser
Install-Module oh-my-posh -Scope CurrentUser
Install-Module -Name PSReadLine -AllowPrerelease -Scope CurrentUser -Force -SkipPublisherCheck
```

## Setup `git`

```shell
New-Item -Type Directory ~/git
cd ~/git
git 
git config --global user.email "email@jaredschmidt.net"
git config --global user.name "Jared Schmidt"
```