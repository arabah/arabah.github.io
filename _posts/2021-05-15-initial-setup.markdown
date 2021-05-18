---
layout: post
title:  "Initial setup on Windows 10"
date:   2021-05-15 21:33:58 -0700
# categories: 
---

1. Windows 10
1. [PowerShell](https://aka.ms/powershell-release?tag=stable)
1. [Visual Studio Code Insiders](https://code.visualstudio.com/insiders/)
1. [Windows Terminal Preview](https://aka.ms/terminal-preview) (Or [Windows Terminal](https://aka.ms/terminal))

    `Set-ExecutionPolicy RemoteSigned -Scope CurrentUser`
1. [oh-my-posh](https://ohmyposh.dev/docs/pwsh/)
  
    `Install-Module oh-my-posh -Scope CurrentUser`
1. [Nerd Fonts](https://www.nerdfonts.com/) (ref: [https://ohmyposh.dev/docs/fonts](https://ohmyposh.dev/docs/fonts))
   
    `Caskaydia Cove Nerd Font`
1. Open Windows Terminal settings in VS Code, under the `profile` JSON section

    ```
    "defaults": {
        "fontFace":  "CaskaydiaCove NF", //"MesloLGM NF",
        "fontSize": 9
    }
    ```
1. [Chocolatey](https://chocolatey.org/)

    `choco install notepadplusplus`

[Setup Git →]({% post_url 2021-05-17-setting-up-git %})
