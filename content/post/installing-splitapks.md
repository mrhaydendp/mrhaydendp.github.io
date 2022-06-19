+++
author = "Hayden Plumley"
title = "Installing Split-Apks Through ADB"
date = "2022-05-16"
description = "How to install split-apk files through adb"
tags = ["Android"]
categories = ["Tutorials"]
+++

## What are They
App Bundles are Google's newest app packaging format for Android. Its benefits include smaller file sizes, faster installation, and 1 unified install bundle. This is achieved by taking an app then splitting it into a base app and feature splits. Splits are for device specific settings like: dpi, arch, and language. Now that we know what App Bundles (Split APKs) are lets install one.

# How to Install on Linux
Install ADB through your package manager:
``` shell
sudo apt install adb
```

Extract file (.apkm for example) to folder:
``` shell
tar -xf testapp.apkm ./Split
```

Run adb install-multiple in Split folder:
``` shell
adb install-multiple ./Split/*
```