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
- [FiraCode nerd font](https://github.com/ryanoasis/nerd-fonts/releases/download/v3.4.0/FiraCode.zip)
- Terminal:
  - WSL (Windows subsystem for linux): `wsl.exe --install`
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
    -    
  - [ZSH](https://ohmyz.sh/) if on Linux
  - [fzf](https://github.com/junegunn/fzf)
  - [zoxide](https://github.com/ajeetdsouza/zoxide)
