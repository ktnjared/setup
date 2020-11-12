# Windows 10 20H2 on Myyah

## Windows 10

### Core OS

#### 1. Install and configure the latest version of [Windows 10][win10_download]

- Create local user
- Privacy Settings page

    | Option             | on/off | Option               | on/off |
    | ------------------ | ------ | -------------------- | ------ |
    | Speech recognition | off    | Location             | on     |
    | Diagnostics        | on     | Tailored experiences | off    |
    | Relevant Ads       | off    |                      |        |

- Cortana off

#### 2. Rename Computer

```powershell
Start-Process -Verb RunAs powershell.exe -Args "Rename-Computer myyah"
```

#### 4. Install all updates from Software Update

1. Settings
2. Updates
3. Check for Updates
4. Install All
5. Reboot
6. Continue to loop until no updates remain
    - Install any optional updates, drivers and firmware.

#### 4. Sign in to OneDrive

Sign in to OneDrive and begin sync. We will need the `.ps1` files in

### Drivers & Dell SupportAssist

#### 1. Install [Dell SupportAssistant][app_supportassitant]

```powershell
$download_dir = $env:userprofile + '\Downloads'
$download_file = "SupportAssistInstaller.exe"
$download_url = "https://downloads.dell.com/serviceability/catalog/SupportAssistInstaller.exe"

Invoke-WebRequest -Uri $download_url -OutFile $download_dir\$download_file
Invoke-Expression $download_dir\$download_file

Remove-Variable download_dir
Remove-Variable download_file
Remove-Variable download_url
```

#### 2. Run all steps

### [Windows Subsystem for Linux][wsl] aka WSL

Installation documentation is [available in Microsoft Docs][wsl_install].

#### 1. Enable WSL

In an elevated PowerShell session (PowerShell as Administrator), run

```powershell
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
```

#### 2. Enable Virtual Machine Platform

In an elevated PowerShell session (PowerShell as Administrator), run

```powershell
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```

#### 3. Reboot

```powershell
Restart-Computer
```

#### 4. Following the reboot, install the [WSL2 Linux Kernel update package for x64 machines][wsl_kernel_update]

```powershell
$download_dir = $env:userprofile + '\Downloads'
$download_file = "wsl_update_x64.msi"
$download_url = "https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi"

Invoke-WebRequest -Uri $download_url -OutFile $download_dir\$download_file
Invoke-Expression $download_dir\$download_file

Remove-Variable download_dir
Remove-Variable download_file
Remove-Variable download_url
```

#### 5. Set WSL 2 a the default version

```powershell
wsl --set-default-version 2
```

#### 6. Install a Linux distribution via the [Microsoft Store][msstore]

| Distro                                      | Website                                        | Microsoft Store                                                          |
| ------------------------------------------- | ---------------------------------------------- | ------------------------------------------------------------------------ |
| [Kali Linux][kali]                          | [https://www.kali.org/docs/wsl/win-kex/][kali] | [https://www.microsoft.com/store/apps/9PKR34TNCV07][msstore_kali]        |
| [Pengwin][pengwin]                          | [https://www.whitewaterfoundry.com/][pengwin]  | [https://www.microsoft.com/store/apps/9NV1GV1PXZ6P][msstore_pengwin]     |
| [Ubuntu][ubuntu] (current release; 20.10)   | [https://ubuntu.com/wsl][ubuntu]               | [https://www.microsoft.com/store/productId/9NBLGGH4MSV6][msstore_ubuntu] |
| [Ubuntu 20.04][ubuntu] (current LTS; 20.04) | [https://ubuntu.com/wsl][ubuntu]               | [https://www.microsoft.com/store/apps/9n6svws3rx71][msstore_ubuntu2004]  |

#### 7. Launch the distribution to initiate setup

## File Explorer (explorer.exe)

### Recycle Bin

1. Add Recycle Bin to Quick Access in File Explorer
2. Remove Recycle Bin from Desktop
    1. Settings
    2. Personalization
    3. Themes
    4. Desktop icon settings
    5. Uncheck *Recycle Bin*
    6. Click *OK*

### Preferences

- Always show full path
- Hide Drive Letters
- Show known file extensions

## [winget][msdocs_winget]

### Install `winget`

GitHub Project at [microsoft/winget-cli][github_winget]

_Note: This process will not be required after `winget` is out of Preview Release. It will be included with Windows 10 eventually._

1. Download latest release of [winget-cli appx][github_winget_release]
2. Install

### Install software with `winget`

| `winget` Name                                | `winget` ID                                 | PowerShell Command                                |
| -------------------------------------------- | ------------------------------------------- | ------------------------------------------------- |
| [1Password][1password]                       | AgileBits.1Password                         | `winget install 1password`                        |
| [7Zip][app_7zip]                             | 7zip.7zip                                   | `winget install 7zip`                             |
| [Auto Dark Mode][app_auto_dark_mode]         | Armin2208.WindowsAutoNightMode              | `winget install "Auto Dark Mode"`                 |
| [Battle. Net][game_bnet]                     | Blizzard.BattleNet                          | `winget install battlenet`                        |
| [Discord][discord]                           | Discord.Discord                             | `winget install discord`                          |
| [EarTrumpet][app_eartrumpet]                 | File-New-Project.EarTrumpet                 | `winget install eartrumpet`                       |
| [f.lux][flux]                                | flux.flux                                   | `winget install flux`                             |
| [Git][git]                                   | Git.Git                                     | `winget install git`                              |
| [Minecraft Launcher][minecraft]              | Mojang.MinecraftLauncher                    | `winget install minecraft`                        |
| [Nvidia GeForce Experience][app_geforce_exp] | Nvidia.GeForceExperience                    | `winget install Nvidia.GeForceExperience`         |
| [OBS Studio][obs]                            | OBSProject.OBSStudio                        | `winget install obs`                              |
| [PowerShell][posh]                           | Microsoft.PowerShell                        | `winget install powershell`                       |
| [PowerToys][app_powertoys]                   | Microsoft.PowerToys                         | `winget install powertoys`                        |
| [Private Internet Access][pia]               | PrivateInternetAccess.PrivateInternetAccess | `winget install pia`                              |
| [Python][python]                             | Python.Python                               | `winget install python`                           |
| [QuickLook][app_quicklook]                   | QL-Win.QuickLook                            | `winget install quicklook`                        |
| [Signal][signal]                             | Signal.Signal                               | `winget install signal`                           |
| [Telegram Desktop][telegram]                 | Telegram.TelegramDesktop                    | `winget install telegram`                         |
| [Twitch App for Windows][app_twitch]         | Twitch.Twitch                               | `winget install twitch`                           |
| [Visual Studio Code][vscode]                 | Microsoft.VisualStudioCode                  | `winget install vscode`                           |
| [Visual Studio Community][visual_studio]     | Microsoft.VisualStudio.Community            | `winget install Microsoft.VisualStudio.Community` |
| [Windows Terminal][terminal]                 | Microsoft.WindowsTerminal                   | `winget install Microsoft.WindowsTerminal`        |

## Windows Terminal

### HOWTO Updating Terminal Settings

Windows Terminal settings are stored in a settings.json file. To edit it, press `CTRL + ,` in Windows Terminal. The file itself is located at `$env:localappdata\Local\Packages\Microsoft.WindowsTerminal_8wekyb3d8bbwe\LocalState\settings.json`.

### Change Default Shell

Change `defaultprofile` to PowerShell 7

```json
"defaultProfile": "{574e775e-4f2a-5b96-ac1e-a2962a402336}",
```

### Change {{fontface}} for PowerShell profile

```json
"fontFace": "Cascadia Code PL"
```

## Final Fantasy XIV

Download client from [https://sqex.to/ffxiv_client_en][game_ffxiv_client] & install.

```powershell
$download_dir = $env:userprofile + '\Downloads'
$download_file = "ffxivsetup.exe"
$download_url = "https://gdl.square-enix.com/ffxiv/inst/ffxivsetup.exe"

Invoke-WebRequest -Uri $download_url -OutFile $download_dir\$download_file
Invoke-Expression $download_dir\$download_file

Remove-Variable download_dir
Remove-Variable download_file
Remove-Variable download_url
```

## EarTrumpet

1. Launch EarTrumpet
2. Remove System Volume from System Tray
    1. Settings
    2. Personalization
    3. Taskbar
    4. Turn system icons on or off
    5. Set *Volume* to **Off**
3. Set *System Sounds* to **20%**

<!-- URLS -->
[1password]: https://1password.com/
[app_auto_dark_mode]: https://github.com/Armin2208/Windows-Auto-Night-Mode
[app_eartrumpet]: https://eartrumpet.app/
[app_geforce_exp]: https://www.nvidia.com/en-us/geforce/geforce-experience/
[app_powertoys]: https://github.com/microsoft/PowerToys
[app_quicklook]: https://pooi.moe/QuickLook/
[app_supportassistant]: https://www.dell.com/support/contents/en-us/article/product-support/self-support-knowledgebase/software-and-downloads/supportassist
[app_twitch]: https://www.twitch.tv/downloads
[bitwarden]: https://bitwarden.com/
[discord]: https://discord.com/
[edge_extensions]: edge://extensions/shortcuts
[flux]: https://justgetflux.com/
[game_bnet]: https://www.blizzard.com/apps/battle.net/desktop
[game_ffxiv_client]: https://sqex.to/ffxiv_client_en
[git]: https://git-scm.com/
[github_winget_release]: https://github.com/microsoft/winget-cli/releases/
[github_winget]: https://github.com/microsoft/winget-cli/
[msdocs_winget]: https://docs.microsoft.com/en-us/windows/package-manager/winget/
[obs]: https://obsproject.com/
[pia]: https://www.privateinternetaccess.com/
[posh]: https://docs.microsoft.com/powershell/
[python]: https://www.python.org/
[signal]: https://signal.org/
[telegram]: https://desktop.telegram.org/
[terminal]: https://docs.microsoft.com/windows/terminal/
[visual_studio]: https://visualstudio.microsoft.com/
[vscode]: https://code.visualstudio.com/
[win10_download]: https://www.microsoft.com/software-download/windows10
[wsl_install]: https://docs.microsoft.com/en-us/windows/wsl/install-win10
[wsl_kernel_update]: https://aka.ms/wsl2kernel
[wsl]: https://docs.microsoft.com/windows/wsl/
[msstore]: https://aka.ms/wslstore
[msstore_kali]: https://www.microsoft.com/store/apps/9PKR34TNCV07
[msstore_pengwin]: https://www.microsoft.com/store/apps/9NV1GV1PXZ6P
[msstore_ubuntu2004]: https://www.microsoft.com/store/apps/9n6svws3rx71
[kali]: https://www.kali.org/docs/wsl/win-kex/
[pengwin]: https://www.whitewaterfoundry.com/
[ubuntu]: https://ubuntu.com/wsl
[app_7zip]: https://www.7-zip.org/
[minecraft]: https://www.minecraft.net/
[msstore_ubuntu]: https://www.microsoft.com/store/productId/9NBLGGH4MSV6
