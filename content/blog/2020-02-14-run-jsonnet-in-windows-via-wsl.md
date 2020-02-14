---
title: Run jsonnet in windows via WSL
date: 2020-02-13T17:44:31.006Z
---
I recently started to use jsonnet, which is a data templating language.

It was hard to find articles and documentation online on how to run jsonnet. I got some issues installing and using jsonnet on windows and thought I could share how I achieved it. 

## Install WSL

First, you will need to enable WSL. You can check out this [article](https://docs.microsoft.com/en-us/windows/wsl/install-win10).

Or run this command in PowerShell (you may need to run PowerShell as an administrator).

> **Note!**
>
>  You will need to restart your computer.

```
Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux
```

You will then need to install a Linux distribution via windows store. I choose Ubuntu 18.04 LTS, you can find it [here](https://www.microsoft.com/sv-se/p/ubuntu-1804-lts/9n9tngvndl3q?rtc=1&activetab=pivot:overviewtab).

## Install Homebrew

You can read the [documentation](https://docs.brew.sh/Homebrew-on-Linux).

Or

1. open wsl by typing **wsl** in powershell or cmd.
2. Install dependencies (Might not be needed)


```
sudo apt-get updatesudo apt-get install binutilssudo apt-get install build-essential
```

3. install homebrew


```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/Linuxbrew/install/master/install.sh)"
```

3. set homebrew in PATH


```
test -d ~/.linuxbrew && eval $(~/.linuxbrew/bin/brew shellenv)test -d /home/linuxbrew/.linuxbrew && eval $(/home/linuxbrew/.linuxbrew/bin/brew shellenv)test -r ~/.bash_profile && echo "eval \$($(brew --prefix)/bin/brew shellenv)" >>~/.bash_profileecho "eval \$($(brew --prefix)/bin/brew shellenv)" >>~/.profile
```

## Install Jsonnet

```
Brew install jsonnet
```

you might need to install gcc. Just run 

```
brew install gcc
```

Now you will be able to run jsonnet.

Btw, to access your C: drive, you can run:

```
cd /mnt/c
```

I hope this was helpful to you
