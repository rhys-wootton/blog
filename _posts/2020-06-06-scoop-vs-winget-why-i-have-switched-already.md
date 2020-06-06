---
layout: post
title: "Scoop vs WinGet: Why I have already switched"
comments: true
---

Around a year ago my ex-boyfriend told me about a package manager/CLI called Scoop. At the time I didn't really know what he was even on about. I knew about package managers on Linux, but I have never had any good experiences with them. They tend to always be behind on versions of programs or not actually host the programs that I use often, and then I have to go and find them on the web myself anyway. Anyhow, I listened to what he said, and went home that day and installed it onto my desktop.

### And that is where my life changed (kinda)

![Image of Scoop Package Manager installing 7-Zip](https://raw.githubusercontent.com/rhys-wootton/blog/master/assets/images/2020-06-06/scoop.png "Look it installed 7-Zip for me!")

It was a bit of a weird tool to get used to. I was so used to searching on Google for the tools that I use, and then downloading an installer and running that. Scoop got rid of that middle man, per say, and by just typing `scoop install [sexy-program]`, it downloaded the program, "installed it" (most of the time it would grab the portable version and just copy it to a directory) and I was good to go. It automatically created start menu shortcuts so I could easily search for the program. I fell in love with it pretty quickly, and that night I made a massive list of programs that I could reinstall with Scoop so it could manage it all for me.

However, after using it for a while I did have my gripes with it. One major problem for me was that it did not automatically delete old versions of a program that it had installed. Whilst it was very easy to update all of my apps that have been installed with Scoop using `scoop update *`, it would never then automatically remove the previous version, and I would end up with a Scoop folder totalling tens of gigabytes full of old versions I would never use. Yes I could easily purge the old versions by simply running `scoop cleanup *`, but it was very easy to forget to do that, and after a month or so, I would have to do it again. It became a big problem on my Dell XPS 15. I have a model with a 128GB SSD that I use to put my programs on, and I would get at least once a month a warning from Windows telling me that disk space was low. 

### Scoop, it's not you it's me, I have found someone else...

Whilst having my issues with Scoop, it still was a very handy tool to have. If I ever needed a program, instead of going onto Google to try and find it, I could just ask Scoop to find and install it for me. That is until I found out that Microsoft ~~[copied a very similar package manager with no acknowledgement](https://www.theverge.com/2020/6/2/21277863/microsoft-winget-windows-package-manager-appget-response-credit-comment)~~ have released their own package manager, **WinGet**. Windows finally has its own package manager, and as soon as I went on GitHub and saw it's initial release, I downloaded it to check it out.

![Image of Windows Package Manager installing 7-Zip](https://raw.githubusercontent.com/rhys-wootton/blog/master/assets/images/2020-06-06/winget.png "Look it installed 7-Zip for me, but into its proper location for a program!")

In a whole lot of ways, it is similar to Scoop. You can search for apps as they call them in the same way as you could with Scoop (`winget search [sexy-app]`), install them (`winget install [sexy-app]`), etcetera. What has won me over with WinGet however are two main things. Installers can be run both interactively or silently. By default they run interactively so I can see the installer if I want, but with a simple `-h` or `--silent` switch, the installer will run silently and not bother me. With Scoop I never had that option, but I cannot really complain about that considering Scoop was made to install programs with minimal user interaction. It's other benefit, however, is that installed apps are actuall installed to where they would usually be by default. I don't have to change any settings in WinGet, they automatically get put in `C:\Program Files`. It means that Windows will also detect them as installed programs, and I can remove them as such in the settings app. 

WinGet is still in its very early years, however, and it still needs polishing up in some places. For example, WinGet currently doesn't install apps with an exact match if there is another app that shares a part of the name (FireFox is a really good example of this, as it has both the stable and beta releases on there). There is also currently no way to see what apps have are installed, and a way to update or uninstall them. I know these are all planned out in the [Windows Package Manager v1.0 Roadmap](https://github.com/microsoft/winget-cli/blob/master/doc/windows-package-manager-v1-roadmap.md).

### So what have we learnt?

A centralised Windows package manager has been wanted for years, so it is good to finally see Microsoft developing one, and it being open-sourced is even nicer! I'd say if you are currently deciding what package manager to use for Windows, play around with WinGet and see if you like it, and any issues you find, open a new issue on their official GitHub page and let them know. If you want something more stable, however, and don't mind programs not being "installed" to Windows per say, go and check out Scoop, it is still a great package manager on its own!

[Click here](https://github.com/microsoft/winget-cli) to check out WinGet, or [click here](https://scoop.sh/) to check out Scoop!