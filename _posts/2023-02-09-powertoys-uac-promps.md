---
layout: post
title: "Stopping Microsoft PowerToys UAC Prompts"
date: 2023-02-09
tags: technology software
---

I recently switched to logging in with a non-admin account on my Windows work computer for increased security. Frustratingly, Microsoft PowerToys continued to cause a UAC (User Account Control) dialog to pop up on Windows login asking "Do you want to allow this app to make changes to your device?" and requiring that I enter my admin account username. This frustration was compounded when working remotely, as my admin account can't authenticate with the domain until my VPN client has been connected, meaning I'd need to click NO on the UAC prompt and remember to launch PowerToys alter after connecting the VPN.

Web searches showed two year old bugs where disabling PowerToys' auto-start feature (and then re-enabling it) fixed this and stopped the UAC prompt. But I learned that even with the setting disabled, PowerToys was launching on start and showing the UAC prompt.

Eventually it dawned on me to delete %AppData%\Local\Microsoft\PowerToys as I suspected some old setting existed there that was overriding new functionality or bug fixes. And sure enough, after doing so, I'm now able to launch PowerToys (on start or manually) without any UAC prompts. 

I’m sharing here in case anyone else is stumped like I was.
