---
view: post
layout: post
lang: en
author: oechiih
title: "Building your PowerShell Modules the smart way"
description: Building your PowerShell Modules doesn't need to be hard or time consuming
excerpt: Building your PowerShell Modules doesn't need to be hard or time consuming
cover: false
coverAlt:
demo:
repos:
  - url: https:\\github.com\rdbartram\PSBuildRelease
    name: PSBuildRelease
  - url: https://github.com/Oechiih/PlasterPSBR
    name: PlasterPSBR
audio:
categories:
  - twss
tags:
  - powershell
created_at: 2019-02-12 08:00
updated_at: 2019-02-12 08:00

meta:
  - property: og:image
    content: /share/dftai-image-share.png   #ToDo
  - name: twitter:image
    content: /share/dftai-image-share.png   #ToDo
---

Lately I found myself tinkering with build and release pipelines for PowerShell modules on Azure DevOps. I remembered my good friend [Ryan Bartram](https://dftai.ch/authors/rdbartram.html) developed a solution for that before so I checked his [GitHub Profile](https://github.com/rdbartram) and in fact found the [PSBuildRelease Repo](https://github.com/rdbartram/PSBuildRelease) which offered many of the things I wanted to do for my pipelines, happy days.
This post is the first part of a series intended to guide you through setting up your PowerShell module development process with PSBuildRelease.
First, credit where credit is due. PSBuildRelease takes advantage of several other open source PowerShell modules:

* [PSDepend](https://github.com/RamblingCookieMonster/PSDepend)
* [Pester](https://github.com/pester/Pester)
* [InvokeBuild](https://github.com/nightroman/Invoke-Build)
* [BuildHelpers](https://github.com/RamblingCookieMonster/BuildHelpers)
* [GitVersion](https://github.com/GitTools/GitVersion)
* [PowerShell Core](https://docs.microsoft.com/en-us/powershell/scripting/install/installing-powershell-core-on-windows?view=powershell-6)

In this first part we'll focus on building our modules locally. I wrote a [Plaster template]('https://github.com/Oechiih/PlasterPSBR') to quickly scaffold a base structure for your module.
You can install the template directly from the Powershellgallery:

``` powershell
Install-Module 'PlasterPSBR' -Scope CurrentUser
```

With that setting up the desired folder structure becomes a breeze. To find the newly installed Plaster template run

``` powershell
Get-PlasterTemplate -IncludeInstalledModules
```
