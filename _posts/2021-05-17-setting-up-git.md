---
layout: post
title: Setting up Git
date: 2021-05-17 21:55 -0700
---

# Install Git

1. In Windows Terminal

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

## Account

```
git config --global user.email "<>"
git config --global user.name "<>"
```

## GPG

### Install GPG

1. In Windows Terminal

    `choco install gnupg`

### Generate GPG key

From [https://docs.github.com/en/github/authenticating-to-github/generating-a-new-gpg-key](https://docs.github.com/en/github/authenticating-to-github/generating-a-new-gpg-key)

1. `gpg --full-generate-key`
1. Key size at least `4096`
1. `gpg --list-secret-keys --keyid-format LONG`
1. Copy the GPG secret key (`sec`)
1. `gpg --armor --export <sec>`
1. Add GPG key to GH account

### Signing Commits

From [https://docs.github.com/en/github/authenticating-to-github/telling-git-about-your-signing-key](https://docs.github.com/en/github/authenticating-to-github/telling-git-about-your-signing-key)

1. `git config --global user.signingkey <sec>`
1. `git config --global commit.gpgsign "true"`
1. `git config --global gpg.program "C:\Program Files (x86)\gnupg\bin\gpg.exe"`

## Troubleshooting

### gpg: signing failed: No secret key

```
➜ arabah.github.io git:(master) gc -m "First commit" --signoff
gpg: directory '/c/Users/user/.gnupg' created
gpg: keybox '/c/Users/user/.gnupg/pubring.kbx' created
gpg: skipped "<>": No secret key
gpg: signing failed: No secret key
error: gpg failed to sign the data
fatal: failed to write commit object
```

#### Solution

`git config --global gpg.program "C:\Program Files (x86)\gnupg\bin\gpg.exe"`

On Windows pwsh, you will need to set git configuration `gpg.program` with the path to `gpg.exe`.
