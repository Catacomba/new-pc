# Fresh PC installation

This will be a repo for my notes when installing a new PC.

This is currently written for windows only. I expect to edit the list when installing a new linux install and adding/separating windows-linux specifics.

- Install Chrome
- Run [Windows debloater](https://github.com/Raphire/Win11Debloat)
- Login gmail
- Login github
- [Ninite](https://ninite.com/7zip-brave-discord-everything-firefox-git-notepadplusplus-paint.net-sharex-spotify-vlc-vscode-windirstat-winrar/):
  - Firefox, Brave
  - Paint.net, ShareX
  - Everything
  - Discord
  - Git
  - Notepad++
  - VSCode
  - VLC
  - Spotify
  - 7zip, Winrar
- Chrome extensions:
  - Vimium
- [WIndows Microsoft PowerToys](https://github.com/microsoft/PowerToys)
- Download and install [FiraCode nerd font](https://github.com/ryanoasis/nerd-fonts/releases/download/v3.4.0/FiraCode.zip)
- [Docker](https://docs.docker.com/desktop/setup/install/windows-install/)
- Terminal:
  - Change default font to FiraCode
  - WSL (Windows subsystem for linux): `wsl.exe --install`
  - TMUX https://github.com/tmux/tmux/wiki
  - [zoxide](https://github.com/ajeetdsouza/zoxide) install this in powershell and wsl   
  - [fzf](https://github.com/junegunn/fzf) install this in powershell and wsl
  - [Oh my posh](https://ohmyposh.dev/docs/installation/windows)
    - Create profile file: `New-Item -Path $PROFILE -Type File -Force` 
    - Open profile file `notepad $PROFILE`
    - Paste into the file:
```pwsh
oh-my-posh init pwsh --config "$env:POSH_THEMES_PATH/M365Princess.omp.json" | Invoke-Expression
# Import the Chocolatey Profile that contains the necessary code to enable
# tab-completions to function for choco.
# Be aware that if you are missing these lines from your profile, tab completion
# for choco will not function.
# See https://ch0.co/tab-completion for details.
$ChocolateyProfile = "$env:ChocolateyInstall\helpers\chocolateyProfile.psm1"
if (Test-Path($ChocolateyProfile)) {
  Import-Module "$ChocolateyProfile"
}

Invoke-Expression (& { (zoxide init powershell | Out-String) })
```
  - Windows terminal config. Open the windows terminal json. Paste in the following code. Dont worry about guids, they get automagically fixed
```json
{
    "$help": "https://aka.ms/terminal-documentation",
    "$schema": "https://aka.ms/terminal-profiles-schema",
    "actions": 
    [
        {
            "command": "unbound",
            "keys": "alt+shift+d"
        },
        {
            "command": "unbound",
            "keys": "ctrl+shift+d"
        },
        {
            "command": "unbound",
            "keys": "ctrl+shift+w"
        },
        {
            "command": 
            {
                "action": "copy",
                "singleLine": false
            },
            "keys": "ctrl+c"
        },
        {
            "command": "paste",
            "keys": "ctrl+v"
        },
        {
            "command": 
            {
                "action": "splitPane",
                "split": "auto",
                "splitMode": "duplicate"
            }
        },
        {
            "command": "find",
            "keys": "ctrl+shift+f"
        }
    ],
    "alwaysShowTabs": true,
    "copyFormatting": "none",
    "copyOnSelect": false,
    "defaultProfile": "{61c54bbd-c2c6-5271-96e7-009a87ff44bf}",
    "newTabMenu": 
    [
        {
            "type": "remainingProfiles"
        }
    ],
    "profiles": 
    {
        "defaults": 
        {
            "adjustIndistinguishableColors": "always",
            "antialiasingMode": "cleartype",
            "backgroundImage": "C:\\Windows\\Web\\Wallpaper\\ThemeA\\img21.jpg",
            "backgroundImageOpacity": 0.31,
            "backgroundImageStretchMode": "uniformToFill",
            "colorScheme": "Catppuccin Frappe",
            "cursorHeight": 1,
            "cursorShape": "emptyBox",
            "elevate": true,
            "experimental.retroTerminalEffect": false,
            "font": 
            {
                "face": "FiraCode Nerd Font"
            },
            "opacity": 77,
            "startingDirectory": "C:\\",
            "useAcrylic": false,
            "useAtlasEngine": true
        },
        "list": 
        [
            {
                "commandline": "%SystemRoot%\\System32\\WindowsPowerShell\\v1.0\\powershell.exe",
                "elevate": true,
                "guid": "{61c54bbd-c2c6-5271-96e7-009a87ff44bf}",
                "hidden": false,
                "name": "Windows PowerShell"
            },
            {
                "commandline": "%SystemRoot%\\System32\\cmd.exe",
                "guid": "{0caa0dad-35be-5f56-a8ff-afceeeaa6101}",
                "hidden": false,
                "name": "Command Prompt"
            },
            {
                "guid": "{b453ae62-4e3d-5e58-b989-0a998ec441b8}",
                "hidden": false,
                "name": "Azure Cloud Shell",
                "source": "Windows.Terminal.Azure"
            },
            {
                "guid": "{16208362-94fc-5b1f-a491-5b2624d5ab56}",
                "hidden": true,
                "name": "Visual Studio Debug Console",
                "source": "VSDebugConsole"
            },
            {
                "guid": "{a1857788-711e-5513-9ded-130eab8930fa}",
                "hidden": true,
                "name": "Developer Command Prompt for VS 2019",
                "source": "Windows.Terminal.VisualStudio"
            },
            {
                "guid": "{f9d9f96b-2198-5167-baad-29ab5bfb8d0a}",
                "hidden": true,
                "name": "Developer PowerShell for VS 2019",
                "source": "Windows.Terminal.VisualStudio"
            },
            {
                "guid": "{51855cb2-8cce-5362-8f54-464b92b32386}",
                "hidden": false,
                "name": "Ubuntu",
                "source": "CanonicalGroupLimited.Ubuntu_79rhkp1fndgsc"
            },
            {
                "guid": "{2c4de342-38b7-51cf-b940-2309a097f518}",
                "hidden": true,
                "name": "Ubuntu",
                "source": "Windows.Terminal.Wsl"
            },
            {
                "commandline": "%WINDIR%\\System32\\WindowsPowerShell\\v1.0\\powershell.exe -ExecutionPolicy ByPass -NoExit -Command \"& 'C:\\Users\\Kevin\\miniconda3\\shell\\condabin\\conda-hook.ps1' ; conda activate 'C:\\Users\\Kevin\\miniconda3' \"",
                "guid": "{baef6041-a2f3-5472-b295-a7d7fb0ed62f}",
                "icon": "C:\\Users\\Kevin\\miniconda3\\Menu\\anaconda_powershell_prompt.ico",
                "name": "Anaconda PowerShell Prompt (miniconda3)",
                "startingDirectory": "C:\\Users\\Kevin"
            },
            {
                "commandline": "%WINDIR%\\System32\\cmd.exe \"/K\" C:\\Users\\Kevin\\miniconda3\\Scripts\\activate.bat C:\\Users\\Kevin\\miniconda3",
                "guid": "{35427e1d-45ad-517a-8692-8d5e4093f90f}",
                "icon": "C:\\Users\\Kevin\\miniconda3\\Menu\\anaconda_prompt.ico",
                "name": "Anaconda Prompt (miniconda3)",
                "startingDirectory": "C:\\Users\\Kevin"
            },
            {
                "guid": "{e0670da9-6007-5c03-8fa1-a15208eacd7d}",
                "hidden": false,
                "name": "docker-desktop-data",
                "source": "Microsoft.WSL"
            },
            {
                "guid": "{74803ecc-5b44-5c72-98d5-4c3f24a7ff2d}",
                "hidden": false,
                "name": "docker-desktop",
                "source": "Microsoft.WSL"
            }
        ]
    },
    "schemes": 
    [
        {
            "background": "#0C0C0C",
            "black": "#0C0C0C",
            "blue": "#0037DA",
            "brightBlack": "#FFFEFE",
            "brightBlue": "#3B78FF",
            "brightCyan": "#61D6D6",
            "brightGreen": "#16C60C",
            "brightPurple": "#B4009E",
            "brightRed": "#E74856",
            "brightWhite": "#F2F2F2",
            "brightYellow": "#F9F1A5",
            "cursorColor": "#FFFFFF",
            "cyan": "#3A96DD",
            "foreground": "#CCCCCC",
            "green": "#13A10E",
            "name": "Campbell",
            "purple": "#881798",
            "red": "#C50F1F",
            "selectionBackground": "#FFFFFF",
            "white": "#CCCCCC",
            "yellow": "#C19C00"
        },
        {
            "background": "#012456",
            "black": "#0C0C0C",
            "blue": "#0037DA",
            "brightBlack": "#767676",
            "brightBlue": "#3B78FF",
            "brightCyan": "#61D6D6",
            "brightGreen": "#16C60C",
            "brightPurple": "#B4009E",
            "brightRed": "#E74856",
            "brightWhite": "#F2F2F2",
            "brightYellow": "#F9F1A5",
            "cursorColor": "#FFFFFF",
            "cyan": "#3A96DD",
            "foreground": "#CCCCCC",
            "green": "#13A10E",
            "name": "Campbell Powershell",
            "purple": "#881798",
            "red": "#C50F1F",
            "selectionBackground": "#FFFFFF",
            "white": "#CCCCCC",
            "yellow": "#C19C00"
        },
        {
            "background": "#303446",
            "black": "#51576D",
            "blue": "#8CAAEE",
            "brightBlack": "#626880",
            "brightBlue": "#8CAAEE",
            "brightCyan": "#81C8BE",
            "brightGreen": "#A6D189",
            "brightPurple": "#F4B8E4",
            "brightRed": "#E78284",
            "brightWhite": "#A5ADCE",
            "brightYellow": "#E5C890",
            "cursorColor": "#F2D5CF",
            "cyan": "#81C8BE",
            "foreground": "#C6D0F5",
            "green": "#A6D189",
            "name": "Catppuccin Frappe",
            "purple": "#F4B8E4",
            "red": "#E78284",
            "selectionBackground": "#626880",
            "white": "#B5BFE2",
            "yellow": "#E5C890"
        },
        {
            "background": "#282C34",
            "black": "#282C34",
            "blue": "#61AFEF",
            "brightBlack": "#5A6374",
            "brightBlue": "#61AFEF",
            "brightCyan": "#56B6C2",
            "brightGreen": "#98C379",
            "brightPurple": "#C678DD",
            "brightRed": "#E06C75",
            "brightWhite": "#DCDFE4",
            "brightYellow": "#E5C07B",
            "cursorColor": "#FFFFFF",
            "cyan": "#56B6C2",
            "foreground": "#DCDFE4",
            "green": "#98C379",
            "name": "One Half Dark",
            "purple": "#C678DD",
            "red": "#E06C75",
            "selectionBackground": "#FFFFFF",
            "white": "#DCDFE4",
            "yellow": "#E5C07B"
        },
        {
            "background": "#FAFAFA",
            "black": "#383A42",
            "blue": "#0184BC",
            "brightBlack": "#4F525D",
            "brightBlue": "#61AFEF",
            "brightCyan": "#56B5C1",
            "brightGreen": "#98C379",
            "brightPurple": "#C577DD",
            "brightRed": "#DF6C75",
            "brightWhite": "#FFFFFF",
            "brightYellow": "#E4C07A",
            "cursorColor": "#4F525D",
            "cyan": "#0997B3",
            "foreground": "#383A42",
            "green": "#50A14F",
            "name": "One Half Light",
            "purple": "#A626A4",
            "red": "#E45649",
            "selectionBackground": "#FFFFFF",
            "white": "#FAFAFA",
            "yellow": "#C18301"
        },
        {
            "background": "#002B36",
            "black": "#002B36",
            "blue": "#268BD2",
            "brightBlack": "#073642",
            "brightBlue": "#839496",
            "brightCyan": "#93A1A1",
            "brightGreen": "#586E75",
            "brightPurple": "#6C71C4",
            "brightRed": "#CB4B16",
            "brightWhite": "#FDF6E3",
            "brightYellow": "#657B83",
            "cursorColor": "#FFFFFF",
            "cyan": "#2AA198",
            "foreground": "#839496",
            "green": "#859900",
            "name": "Solarized Dark",
            "purple": "#D33682",
            "red": "#DC322F",
            "selectionBackground": "#FFFFFF",
            "white": "#EEE8D5",
            "yellow": "#B58900"
        },
        {
            "background": "#FDF6E3",
            "black": "#002B36",
            "blue": "#268BD2",
            "brightBlack": "#073642",
            "brightBlue": "#839496",
            "brightCyan": "#93A1A1",
            "brightGreen": "#586E75",
            "brightPurple": "#6C71C4",
            "brightRed": "#CB4B16",
            "brightWhite": "#FDF6E3",
            "brightYellow": "#657B83",
            "cursorColor": "#002B36",
            "cyan": "#2AA198",
            "foreground": "#657B83",
            "green": "#859900",
            "name": "Solarized Light",
            "purple": "#D33682",
            "red": "#DC322F",
            "selectionBackground": "#FFFFFF",
            "white": "#EEE8D5",
            "yellow": "#B58900"
        },
        {
            "background": "#000000",
            "black": "#000000",
            "blue": "#3465A4",
            "brightBlack": "#555753",
            "brightBlue": "#729FCF",
            "brightCyan": "#34E2E2",
            "brightGreen": "#8AE234",
            "brightPurple": "#AD7FA8",
            "brightRed": "#EF2929",
            "brightWhite": "#EEEEEC",
            "brightYellow": "#FCE94F",
            "cursorColor": "#FFFFFF",
            "cyan": "#06989A",
            "foreground": "#D3D7CF",
            "green": "#4E9A06",
            "name": "Tango Dark",
            "purple": "#75507B",
            "red": "#CC0000",
            "selectionBackground": "#FFFFFF",
            "white": "#D3D7CF",
            "yellow": "#C4A000"
        },
        {
            "background": "#FFFFFF",
            "black": "#000000",
            "blue": "#3465A4",
            "brightBlack": "#555753",
            "brightBlue": "#729FCF",
            "brightCyan": "#34E2E2",
            "brightGreen": "#8AE234",
            "brightPurple": "#AD7FA8",
            "brightRed": "#EF2929",
            "brightWhite": "#EEEEEC",
            "brightYellow": "#FCE94F",
            "cursorColor": "#000000",
            "cyan": "#06989A",
            "foreground": "#555753",
            "green": "#4E9A06",
            "name": "Tango Light",
            "purple": "#75507B",
            "red": "#CC0000",
            "selectionBackground": "#FFFFFF",
            "white": "#D3D7CF",
            "yellow": "#C4A000"
        },
        {
            "background": "#300A24",
            "black": "#171421",
            "blue": "#0037DA",
            "brightBlack": "#767676",
            "brightBlue": "#08458F",
            "brightCyan": "#2C9FB3",
            "brightGreen": "#26A269",
            "brightPurple": "#A347BA",
            "brightRed": "#C01C28",
            "brightWhite": "#F2F2F2",
            "brightYellow": "#A2734C",
            "cursorColor": "#FFFFFF",
            "cyan": "#3A96DD",
            "foreground": "#FFFFFF",
            "green": "#26A269",
            "name": "Ubuntu-ColorScheme",
            "purple": "#881798",
            "red": "#C21A23",
            "selectionBackground": "#FFFFFF",
            "white": "#CCCCCC",
            "yellow": "#A2734C"
        },
        {
            "background": "#000000",
            "black": "#000000",
            "blue": "#000080",
            "brightBlack": "#808080",
            "brightBlue": "#0000FF",
            "brightCyan": "#00FFFF",
            "brightGreen": "#00FF00",
            "brightPurple": "#FF00FF",
            "brightRed": "#FF0000",
            "brightWhite": "#FFFFFF",
            "brightYellow": "#FFFF00",
            "cursorColor": "#FFFFFF",
            "cyan": "#008080",
            "foreground": "#C0C0C0",
            "green": "#008000",
            "name": "Vintage",
            "purple": "#800080",
            "red": "#800000",
            "selectionBackground": "#FFFFFF",
            "white": "#C0C0C0",
            "yellow": "#808000"
        },
        {
            "background": "#000000",
            "black": "#0C0C0C",
            "blue": "#0037DA",
            "brightBlack": "#767676",
            "brightBlue": "#3B78FF",
            "brightCyan": "#61D6D6",
            "brightGreen": "#16C60C",
            "brightPurple": "#B4009E",
            "brightRed": "#E74856",
            "brightWhite": "#F2F2F2",
            "brightYellow": "#F9F1A5",
            "cursorColor": "#FFFFFF",
            "cyan": "#3A96DD",
            "foreground": "#FFFFFF",
            "green": "#13A10E",
            "name": "_My color scheme",
            "purple": "#881798",
            "red": "#C50F1F",
            "selectionBackground": "#FFFFFF",
            "white": "#CCCCCC",
            "yellow": "#C19C00"
        }
    ],
    "showTabsInTitlebar": true,
    "tabWidthMode": "titleLength",
    "themes": 
    [
        {
            "name": "Catppuccin Frappe",
            "tab": 
            {
                "background": "#303446FF",
                "showCloseButton": "always",
                "unfocusedBackground": null
            },
            "tabRow": 
            {
                "background": "#292C3CFF",
                "unfocusedBackground": "#232634FF"
            },
            "window": 
            {
                "applicationTheme": "dark",
                "useMica": false
            }
        }
    ],
    "useAcrylicInTabRow": true
}
```

# ZSH via WSL
  - [eza](https://github.com/eza-community/eza)
  - [ZSH](https://ohmyz.sh/) if on Linux or pimping WSL
  - Install nodejs:
    - Make sure to install it via wsl, pick [for linux, via nvm](https://nodejs.org/en/download)
  - Install angular `npm install -g @angular/cli` (you need this to get the `ng` command)
  - Install cargo `curl https://sh.rustup.rs -sSf | sh` (I use rust on some other project, since i want to just copy/paste my zsh config, i need it everywhere)
  - Install zsh-syntax-highlight `git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting`
  - Install powerlevel10k git clone --depth=1 https://github.com/romkatv/powerlevel10k.git "${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k"
  - Copy the following p10k config into ~/.p10k.zsh
```
# Generated by Powerlevel10k configuration wizard on 2024-10-15 at 13:05 CEST.
# Based on romkatv/powerlevel10k/config/p10k-pure.zsh, checksum 07533.
# Wizard options: nerdfont-v3 + powerline, small icons, pure, original, rprompt,
# 24h time, 2 lines, sparse, instant_prompt=verbose.
# Type `p10k configure` to generate another config.
#
# Config file for Powerlevel10k with the style of Pure (https://github.com/sindresorhus/pure).
#
# Differences from Pure:
#
#   - Git:
#     - `@c4d3ec2c` instead of something like `v1.4.0~11` when in detached HEAD state.
#     - No automatic `git fetch` (the same as in Pure with `PURE_GIT_PULL=0`).
#
# Apart from the differences listed above, the replication of Pure prompt is exact. This includes
# even the questionable parts. For example, just like in Pure, there is no indication of Git status
# being stale; prompt symbol is the same in command, visual and overwrite vi modes; when prompt
# doesn't fit on one line, it wraps around with no attempt to shorten it.
#
# If you like the general style of Pure but not particularly attached to all its quirks, type
# `p10k configure` and pick "Lean" style. This will give you slick minimalist prompt while taking
# advantage of Powerlevel10k features that aren't present in Pure.

# Temporarily change options.
'builtin' 'local' '-a' 'p10k_config_opts'
[[ ! -o 'aliases'         ]] || p10k_config_opts+=('aliases')
[[ ! -o 'sh_glob'         ]] || p10k_config_opts+=('sh_glob')
[[ ! -o 'no_brace_expand' ]] || p10k_config_opts+=('no_brace_expand')
'builtin' 'setopt' 'no_aliases' 'no_sh_glob' 'brace_expand'

() {
  emulate -L zsh -o extended_glob

  # Unset all configuration options.
  unset -m '(POWERLEVEL9K_*|DEFAULT_USER)~POWERLEVEL9K_GITSTATUS_DIR'

  # Zsh >= 5.1 is required.
  [[ $ZSH_VERSION == (5.<1->*|<6->.*) ]] || return

  # Prompt colors.
  local grey='242'
  local red='1'
  local yellow='3'
  local blue='4'
  local magenta='5'
  local cyan='6'
  local white='7'

  # Left prompt segments.
  typeset -g POWERLEVEL9K_LEFT_PROMPT_ELEMENTS=(
    # =========================[ Line #1 ]=========================
    # context                 # user@host
    dir                       # current directory
    vcs                       # git status
    # command_execution_time  # previous command duration
    # =========================[ Line #2 ]=========================
    newline                   # \n
    # virtualenv              # python virtual environment
    prompt_char               # prompt symbol
  )

  # Right prompt segments.
  typeset -g POWERLEVEL9K_RIGHT_PROMPT_ELEMENTS=(
    # =========================[ Line #1 ]=========================
    command_execution_time    # previous command duration
    virtualenv                # python virtual environment
    context                   # user@host
    time                      # current time
    # =========================[ Line #2 ]=========================
    newline                   # \n
  )

  # Basic style options that define the overall prompt look.
  typeset -g POWERLEVEL9K_BACKGROUND=                            # transparent background
  typeset -g POWERLEVEL9K_{LEFT,RIGHT}_{LEFT,RIGHT}_WHITESPACE=  # no surrounding whitespace
  typeset -g POWERLEVEL9K_{LEFT,RIGHT}_SUBSEGMENT_SEPARATOR=' '  # separate segments with a space
  typeset -g POWERLEVEL9K_{LEFT,RIGHT}_SEGMENT_SEPARATOR=        # no end-of-line symbol
  typeset -g POWERLEVEL9K_VISUAL_IDENTIFIER_EXPANSION=           # no segment icons

  # Add an empty line before each prompt except the first. This doesn't emulate the bug
  # in Pure that makes prompt drift down whenever you use the Alt-C binding from fzf or similar.
  typeset -g POWERLEVEL9K_PROMPT_ADD_NEWLINE=true

  # Magenta prompt symbol if the last command succeeded.
  typeset -g POWERLEVEL9K_PROMPT_CHAR_OK_{VIINS,VICMD,VIVIS}_FOREGROUND=$magenta
  # Red prompt symbol if the last command failed.
  typeset -g POWERLEVEL9K_PROMPT_CHAR_ERROR_{VIINS,VICMD,VIVIS}_FOREGROUND=$red
  # Default prompt symbol.
  typeset -g POWERLEVEL9K_PROMPT_CHAR_{OK,ERROR}_VIINS_CONTENT_EXPANSION='❯'
  # Prompt symbol in command vi mode.
  typeset -g POWERLEVEL9K_PROMPT_CHAR_{OK,ERROR}_VICMD_CONTENT_EXPANSION='❮'
  # Prompt symbol in visual vi mode is the same as in command mode.
  typeset -g POWERLEVEL9K_PROMPT_CHAR_{OK,ERROR}_VIVIS_CONTENT_EXPANSION='❮'
  # Prompt symbol in overwrite vi mode is the same as in command mode.
  typeset -g POWERLEVEL9K_PROMPT_CHAR_OVERWRITE_STATE=false

  # Grey Python Virtual Environment.
  typeset -g POWERLEVEL9K_VIRTUALENV_FOREGROUND=$grey
  # Don't show Python version.
  typeset -g POWERLEVEL9K_VIRTUALENV_SHOW_PYTHON_VERSION=false
  typeset -g POWERLEVEL9K_VIRTUALENV_{LEFT,RIGHT}_DELIMITER=

  # Blue current directory.
  typeset -g POWERLEVEL9K_DIR_FOREGROUND=$blue

  # Context format when root: user@host. The first part white, the rest grey.
  typeset -g POWERLEVEL9K_CONTEXT_ROOT_TEMPLATE="%F{$white}%n%f%F{$grey}@%m%f"
  # Context format when not root: user@host. The whole thing grey.
  typeset -g POWERLEVEL9K_CONTEXT_TEMPLATE="%F{$grey}%n@%m%f"
  # Don't show context unless root or in SSH.
  typeset -g POWERLEVEL9K_CONTEXT_{DEFAULT,SUDO}_CONTENT_EXPANSION=

  # Show previous command duration only if it's >= 5s.
  typeset -g POWERLEVEL9K_COMMAND_EXECUTION_TIME_THRESHOLD=5
  # Don't show fractional seconds. Thus, 7s rather than 7.3s.
  typeset -g POWERLEVEL9K_COMMAND_EXECUTION_TIME_PRECISION=0
  # Duration format: 1d 2h 3m 4s.
  typeset -g POWERLEVEL9K_COMMAND_EXECUTION_TIME_FORMAT='d h m s'
  # Yellow previous command duration.
  typeset -g POWERLEVEL9K_COMMAND_EXECUTION_TIME_FOREGROUND=$yellow

  # Grey Git prompt. This makes stale prompts indistinguishable from up-to-date ones.
  typeset -g POWERLEVEL9K_VCS_FOREGROUND=$grey

  # Disable async loading indicator to make directories that aren't Git repositories
  # indistinguishable from large Git repositories without known state.
  typeset -g POWERLEVEL9K_VCS_LOADING_TEXT=

  # Don't wait for Git status even for a millisecond, so that prompt always updates
  # asynchronously when Git state changes.
  typeset -g POWERLEVEL9K_VCS_MAX_SYNC_LATENCY_SECONDS=0

  # Cyan ahead/behind arrows.
  typeset -g POWERLEVEL9K_VCS_{INCOMING,OUTGOING}_CHANGESFORMAT_FOREGROUND=$cyan
  # Don't show remote branch, current tag or stashes.
  typeset -g POWERLEVEL9K_VCS_GIT_HOOKS=(vcs-detect-changes git-untracked git-aheadbehind)
  # Don't show the branch icon.
  typeset -g POWERLEVEL9K_VCS_BRANCH_ICON=
  # When in detached HEAD state, show @commit where branch normally goes.
  typeset -g POWERLEVEL9K_VCS_COMMIT_ICON='@'
  # Don't show staged, unstaged, untracked indicators.
  typeset -g POWERLEVEL9K_VCS_{STAGED,UNSTAGED,UNTRACKED}_ICON=
  # Show '*' when there are staged, unstaged or untracked files.
  typeset -g POWERLEVEL9K_VCS_DIRTY_ICON='*'
  # Show '⇣' if local branch is behind remote.
  typeset -g POWERLEVEL9K_VCS_INCOMING_CHANGES_ICON=':⇣'
  # Show '⇡' if local branch is ahead of remote.
  typeset -g POWERLEVEL9K_VCS_OUTGOING_CHANGES_ICON=':⇡'
  # Don't show the number of commits next to the ahead/behind arrows.
  typeset -g POWERLEVEL9K_VCS_{COMMITS_AHEAD,COMMITS_BEHIND}_MAX_NUM=1
  # Remove space between '⇣' and '⇡' and all trailing spaces.
  typeset -g POWERLEVEL9K_VCS_CONTENT_EXPANSION='${${${P9K_CONTENT/⇣* :⇡/⇣⇡}// }//:/ }'

  # Grey current time.
  typeset -g POWERLEVEL9K_TIME_FOREGROUND=$grey
  # Format for the current time: 09:51:02. See `man 3 strftime`.
  typeset -g POWERLEVEL9K_TIME_FORMAT='%D{%H:%M:%S}'
  # If set to true, time will update when you hit enter. This way prompts for the past
  # commands will contain the start times of their commands rather than the end times of
  # their preceding commands.
  typeset -g POWERLEVEL9K_TIME_UPDATE_ON_COMMAND=false

  # Transient prompt works similarly to the builtin transient_rprompt option. It trims down prompt
  # when accepting a command line. Supported values:
  #
  #   - off:      Don't change prompt when accepting a command line.
  #   - always:   Trim down prompt when accepting a command line.
  #   - same-dir: Trim down prompt when accepting a command line unless this is the first command
  #               typed after changing current working directory.
  typeset -g POWERLEVEL9K_TRANSIENT_PROMPT=off

  # Instant prompt mode.
  #
  #   - off:     Disable instant prompt. Choose this if you've tried instant prompt and found
  #              it incompatible with your zsh configuration files.
  #   - quiet:   Enable instant prompt and don't print warnings when detecting console output
  #              during zsh initialization. Choose this if you've read and understood
  #              https://github.com/romkatv/powerlevel10k#instant-prompt.
  #   - verbose: Enable instant prompt and print a warning when detecting console output during
  #              zsh initialization. Choose this if you've never tried instant prompt, haven't
  #              seen the warning, or if you are unsure what this all means.
  typeset -g POWERLEVEL9K_INSTANT_PROMPT=verbose

  # Hot reload allows you to change POWERLEVEL9K options after Powerlevel10k has been initialized.
  # For example, you can type POWERLEVEL9K_BACKGROUND=red and see your prompt turn red. Hot reload
  # can slow down prompt by 1-2 milliseconds, so it's better to keep it turned off unless you
  # really need it.
  typeset -g POWERLEVEL9K_DISABLE_HOT_RELOAD=true

  # If p10k is already loaded, reload configuration.
  # This works even with POWERLEVEL9K_DISABLE_HOT_RELOAD=true.
  (( ! $+functions[p10k] )) || p10k reload
}

# Tell `p10k configure` which file it should overwrite.
typeset -g POWERLEVEL9K_CONFIG_FILE=${${(%):-%x}:a}

(( ${#p10k_config_opts} )) && setopt ${p10k_config_opts[@]}
'builtin' 'unset' 'p10k_config_opts'
``` 
  - Download cattpuccin mocha into ~/_repos/.
```shell
mkdir ~/_repos
cd ~/_repos
git clone https://github.com/catppuccin/zsh-syntax-highlighting/tree/main
```
- Paste the following into ~/.zshrc after installing zsh:
```bash
# Enable Powerlevel10k instant prompt. Should stay close to the top of ~/.zshrc.
# Initialization code that may require console input (password prompts, [y/n]
# confirmations, etc.) must go above this block; everything else may go below.
if [[ -r "${XDG_CACHE_HOME:-$HOME/.cache}/p10k-instant-prompt-${(%):-%n}.zsh" ]]; then
  source "${XDG_CACHE_HOME:-$HOME/.cache}/p10k-instant-prompt-${(%):-%n}.zsh"
fi

# If you come from bash you might have to change your $PATH.
# export PATH=$HOME/bin:$HOME/.local/bin:/usr/local/bin:$PATH

# Path to your Oh My Zsh installation.
export ZSH="$HOME/.oh-my-zsh"

# Set name of the theme to load --- if set to "random", it will
# load a random theme each time Oh My Zsh is loaded, in which case,
# to know which specific one was loaded, run: echo $RANDOM_THEME
# See https://github.com/ohmyzsh/ohmyzsh/wiki/Themes
ZSH_THEME="powerlevel10k/powerlevel10k"

# Set list of themes to pick from when loading at random
# Setting this variable when ZSH_THEME=random will cause zsh to load
# a theme from this variable instead of looking in $ZSH/themes/
# If set to an empty array, this variable will have no effect.
# ZSH_THEME_RANDOM_CANDIDATES=( "robbyrussell" "agnoster" )

# Uncomment the following line to use case-sensitive completion.
# CASE_SENSITIVE="true"

# Uncomment the following line to use hyphen-insensitive completion.
# Case-sensitive completion must be off. _ and - will be interchangeable.
# HYPHEN_INSENSITIVE="true"

# Uncomment one of the following lines to change the auto-update behavior
# zstyle ':omz:update' mode disabled  # disable automatic updates
# zstyle ':omz:update' mode auto      # update automatically without asking
# zstyle ':omz:update' mode reminder  # just remind me to update when it's time

# Uncomment the following line to change how often to auto-update (in days).
# zstyle ':omz:update' frequency 13

# Uncomment the following line if pasting URLs and other text is messed up.
# DISABLE_MAGIC_FUNCTIONS="true"

# Uncomment the following line to disable colors in ls.
# DISABLE_LS_COLORS="true"

# Uncomment the following line to disable auto-setting terminal title.
# DISABLE_AUTO_TITLE="true"

# Uncomment the following line to enable command auto-correction.
# ENABLE_CORRECTION="true"

# Uncomment the following line to display red dots whilst waiting for completion.
# You can also set it to another string to have that shown instead of the default red dots.
# e.g. COMPLETION_WAITING_DOTS="%F{yellow}waiting...%f"
# Caution: this setting can cause issues with multiline prompts in zsh < 5.7.1 (see #5765)
# COMPLETION_WAITING_DOTS="true"

# Uncomment the following line if you want to disable marking untracked files
# under VCS as dirty. This makes repository status check for large repositories
# much, much faster.
# DISABLE_UNTRACKED_FILES_DIRTY="true"

# Uncomment the following line if you want to change the command execution time
# stamp shown in the history command output.
# You can set one of the optional three formats:
# "mm/dd/yyyy"|"dd.mm.yyyy"|"yyyy-mm-dd"
# or set a custom format using the strftime function format specifications,
# see 'man strftime' for details.
# HIST_STAMPS="mm/dd/yyyy"

# Would you like to use another custom folder than $ZSH/custom?
# ZSH_CUSTOM=/path/to/new-custom-folder

# Source cattpuccing syntax highlighting
source ~/_repos/zsh-syntax-highlighting/themes/catppuccin_mocha-zsh-syntax-highlighting.zsh


# Which plugins would you like to load?
# Standard plugins can be found in $ZSH/plugins/
# Custom plugins may be added to $ZSH_CUSTOM/plugins/
# Example format: plugins=(rails git textmate ruby lighthouse)
# Add wisely, as too many plugins slow down shell startup.
plugins=(git zsh-syntax-highlighting)

source $ZSH/oh-my-zsh.sh

# User configuration

# export MANPATH="/usr/local/man:$MANPATH"

# You may need to manually set your language environment
# export LANG=en_US.UTF-8

# Preferred editor for local and remote sessions
# if [[ -n $SSH_CONNECTION ]]; then
#   export EDITOR='vim'
# else
#   export EDITOR='nvim'
# fi

# Compilation flags
# export ARCHFLAGS="-arch $(uname -m)"

# Set personal aliases, overriding those provided by Oh My Zsh libs,
# plugins, and themes. Aliases can be placed here, though Oh My Zsh
# users are encouraged to define aliases within a top-level file in
# the $ZSH_CUSTOM folder, with .zsh extension. Examples:
# - $ZSH_CUSTOM/aliases.zsh
# - $ZSH_CUSTOM/macos.zsh
# For a full list of active aliases, run `alias`.
#
# Example aliases
alias zshconfig="mate ~/.zshrc"
alias ls="eza -a --icons=always --group-directories-first"
alias obsidian="~/Apps/Obsidian --no-sandbox"
# alias ohmyzsh="mate ~/.oh-my-zsh"
#
export PATH="$PATH:/opt/nvim-linux64/bin:/home/kevin/.local/bin"
eval "$(zoxide init zsh)"

export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion

# Add lampp to path
export PATH="$PATH:/opt/lampp"
# Add lampp php to path
export PATH="$PATH:/opt/lampp/bin/php"

# To customize prompt, run `p10k configure` or edit ~/.p10k.zsh.
[[ ! -f ~/.p10k.zsh ]] || source ~/.p10k.zsh

eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"

[ -f ~/.fzf.zsh ] && source ~/.fzf.zsh


# Load Angular CLI autocompletion.
source <(ng completion script)

# Load cargo.
. "$HOME/.cargo/env"
```
# Tmux via WSL

Install tmux with: `sudo apt install tmux`

Copy the following config into `~/.tmux.conf`
```
# Enable mouse support for scrolling
set -g mouse on

# Start window numbering at 1, not 0
set -g base-index 1
setw -g pane-base-index 1
```

# NVIM via WSL

- `sudo apt-get install unzip ripgrep`
- `sudo apt install build-essential libreadline-dev unzip`
- `brew install luarocks`
- `sudo apt install fd-find`
- `sudo apt install lua5.1 liblua5.1-dev`
- `sudp apt install python3 python3-pip`
- `sudo apt install python3.12-venv`
- Run nvim and use the command :checkhealth to see if anything is missing or not correct

Install [treesitter](https://github.com/nvim-treesitter/nvim-treesitter?tab=readme-ov-file) prerequisites:
  - Requirements for installing tree-sitter-cli: `sudo apt install build-essential clang libclang-dev`
  - `cargo install --locked tree-sitter-cli`

Install nvim:
Download the latest nvim files: https://neovim.io/doc/install/#install-from-download

Create a symbolic link with `sudo ln -s /opt/nvim-linux-x86_64/bin/nvim /usr/local/bin/nvim`, so that the shell knows the location of nvim. 

Extract the files with `tar -xzvf [FILENAME] -C /opt`. This will extract it into `/opt`. This should enable you to run `nvim`. If this does not work, check .zshrc and fix ur path to nvim.

Check if nvim is working with `nvim --clean`. This will load without config.

Install the config: `git clone https://github.com/Catacomba/kickstart.nvim.git "${XDG_CONFIG_HOME:-$HOME/.config}"/nvim`

Start `nvim` and restart it a few times.
Failed to run `config` for nvim-treesitter
