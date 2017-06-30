# Linux game release guide
A guide for (indie) game developers. WIP.

## Introduction
Lorem ipsum

## Targeted distribution
No matter what everyone else says, it should be **Ubuntu**. Why? Because:

* It is the [most][1] [popular][2] [distribution][3] over there.
* There is an actual company behind it - Canonical.
* It is a distribution officially supported by Steam, GOG and Unity.

You should pick a latest LTS (long-term-support) version of Ubuntu - they are released every 2 years and supported for 5 years by Canonical.

Don't worry, your project compiled on Ubuntu will also work on other Linux distributions! However, picking the most popular platform for building and testing your game matters a lot.

## 64 or 32 bit
**64 bit** is the only viable option, for the following reasons:

* I think it is safe to say that 64 bit systems are used by over ~90-95% of Linux users (see sources to "Targeted distribution").
* Unlike on Windows and macOS, 32 bit software DOES NOT WORK on 64 bit Linux systems, unless the user manually installs compatibility libraries - and even with these, there are known issues with it.

However, if there is no other option than using 32 bit (because of a legacy codebase, middleware or engine limitations), your game will still work on Linux after doing some shenanigans.

## Interesting links

https://www.youtube.com/watch?v=WYdOQ_k6YvI


[Sources]
[1]: https://www.gamingonlinux.com/users/statistics
[2]: http://store.steampowered.com/hwsurvey/?platform=linux
[3]: https://stackoverflow.com/research/developer-survey-2016#technology-desktop-operating-system

#### TODO:

* Sources the proper ^way^.
* Explaining the situation with stores, Steam runtime.
* Most popular engines.
* Outsourcing