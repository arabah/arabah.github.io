---
layout: post
title:  "Initial setup on Windows 10"
date:   2021-05-15 21:33:58 -0700
# categories: 
---

1. Windows 10
1. [PowerShell](https://aka.ms/powershell-release?tag=stable)
1. [Windows Terminal Preview](https://aka.ms/terminal-preview) (Or [Windows Terminal](https://aka.ms/terminal))

    `Set-ExecutionPolicy RemoteSigned -Scope CurrentUser`
1. [oh-my-posh](https://ohmyposh.dev/docs/pwsh/)
  
    `Install-Module oh-my-posh -Scope CurrentUser`
1. [Nerd Fonts](https://www.nerdfonts.com/) (ref: [https://ohmyposh.dev/docs/fonts](https://ohmyposh.dev/docs/fonts))
   
    `Caskaydia Cove Nerd Font`
1. Open Windows Terminal settings, under `profile`

    ```
    "defaults": {
        "fontFace":  "CaskaydiaCove NF", //"MesloLGM NF",
        "fontSize": 9
    }
    ```
1. [Visual Studio Code Insiders](https://code.visualstudio.com/insiders/)
1. [Chocolatey](https://chocolatey.org/)

    `choco install git`
1. [posh-git](https://github.com/dahlbyk/posh-git)

    `choco install poshgit`
1. [powershell-git-aliases](https://github.com/gluons/powershell-git-aliases)

    `Install-Module git-aliases -Scope CurrentUser -AllowClobber`
1. In Powershell `notepad $profile`

    ```
    Set-PoshPrompt -Theme robbyrussel

    Import-Module posh-git
    ```
