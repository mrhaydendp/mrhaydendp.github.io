+++
author = "Hayden Plumley"
title = "Installing Winget"
date = "2022-05-16"
description = "How to install Winget in a few simple commands."
tags = ["Windows"]
categories = ["Tutorials"]
+++

Winget is a package manager based of [Keivan Beigi's AppGet](https://keivan.io/the-day-appget-died/), its goal is to be a "one stop shop" to install all your Windows programs. It achieves this by having a central repository of installation scripts for all of your favorite applications such as Discord, Spotify, and Steam. As of now Winget has to be manually installed but later on it should come bundled with Windows.

## Windows Store Method
Direct Link to Open Winget in Windows Store:

[View in Store](ms-windows-store://pdp/?ProductId=9NBLGGH4NNS1)

## PowerShell Method
Here are the 2 commands you have to run to get Winget installed:
``` powershell
# Grab Latest Release URL From GitHub
$latest = (Invoke-WebRequest -UseBasicParsing -URI "https://github.com/microsoft/winget-cli/releases/latest").Links.Href | Select-String ".msixbundle"

# Download With BitsTransfer & Run w/ App Installer
Start-BitsTransfer -Source "https://github.com$latest"; .\Microsoft.DesktopAppInstaller_*.msixbundle
```

## How to Use Winget

| Command                    | Description                     |
|----------------------------|---------------------------------|
| winget install "appname"   | Install specified application   |
| winget uninstall "appname" | Uninstall specified application |
| winget upgrade "appname"   | Update specified application    |
| winget upgrade --all       | Update all supported applications   |
