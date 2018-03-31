# Supporting Linux with your game
A guide for (indie) game developers. Work in progress.

## Introduction
Hello!

Since you're here it probably means that you're planning to release your game on Linux. I am not gonna interfere with how you're gonna port it - there's a big chance that the engine or tools you're using have you already covered. If not, [consider hiring professionals][professionals]. Instead, in this article I will focus on looking on your product a bit more from the user perspective. Here's a couple of points that you absolutely have to be familiar with to ensure high quality of Linux support for your game.

If you have any questions regarding this text, Linux gaming support in general or would like some professional advice on the subject, feel free to contact me using my [email address][address] or [Twitter][twitter].

Let's begin.

## Targeted platform
First of all, you must decide what platform you're going to actually target. This choice will determine what system you will be using to compile your game and to test it. It's supposed to be just "Linux", right? It's actually not that simple. 

### Distribution of choice
You might have probably heard already about the fragmentation of Linux desktop. Many companies claim that supporting Linux is impossible because there are too many distributions and it's too problematic to test on all of them. The good news, is that it's just not true. In general, software compiled on one Linux system will work on all of them. All you need to do is to pick a single distro. But which one?

Asking this question on Reddit will probably start another comment war. Many vocal, often angry people will try to convince you that ArchLinux, Solus or Fedora are used by the core group of Linux users.

No matter what everyone else says, it should be **[Ubuntu][ubuntu]**. Why? Because:

* It is the [most][gol_stats] [popular][steam_stats] [distribution][so_stats] out there.
* It's release based.
* It has commercial backing by a reasonably sized company, [Canonical][canonical].
* It is a distribution officially supported by [Steam][steam_supported], [GOG][gog_supported], [Unity][unity_supported] and [Unreal][unreal_supported].
* A lot of other popular distributions are based on it (Mint, elementaryOS etc.)

You should pick the current latest **LTS (long-term-support)** version of Ubuntu - they are released every 2 years and supported for 5 years by Canonical.

The installation should be **64 bit** for building purposes.

### Other distributions
An important thing to do is to learn basics of Linux distributions family tree: for example, Ubuntu is based on Debian, Lubuntu, Kubuntu, Xubuntu, Mint, elementaryOS are all based on Ubuntu etc. In theory their corresponding releases have full binary compatibility, so in this case your product also supports these without any additional cost.

You can easily check on [DistroWatch][distrowatch] what any distribution is based upon.

## Shipping game files

### 64 or 32 bit binaries
Even though 32 bit hardware is slowly becoming non existent among gamers, developing and releasing 32 bit binaries is still a massive trend in the Windows area. Here, things are a little bit different.

 **64 bit** is the only viable option for your game executable, for the following reasons:

* I think it is safe to say that 64 bit systems are used by over [~90-95% of Linux users][gol_stats].
* Unlike on Windows and macOS, 32 bit software **DOES NOT RUN** by default on 64 bit Linux systems, unless the user manually installs compatibility libraries - and even with these, there are known issues that might appear.

However, if you have no other option than 32 bit (because of a legacy codebase, middleware or engine limitations), your game will still work on Linux after additional steps performed by the end user.

### Library dependencies
One of the common mistakes made by game developers is shipping just the game binary and the assets, forgetting that it won't run without all software it is depending on, like SDL, OpenAL, Mono or Java runtime etc. Having your players fix it on their own is a bad for user experience.

Always remember to put the needed by your software libraries in the distributed package. You can use ```ldd``` command to find out what should be included. Always attempt to run your project on a completely fresh installation of Ubuntu before you release it. If it doesn't start, read the terminal output.

## GPU drivers

*Work in progress draft:*

- Two kinds of drivers:
    - Mesa (opensource by community and vendor - Intel & AMD)
    - proprietary (by vendor - NVIDIA)
- Newer drivers mean more features, better support.
- Updating often solves all issues

## Testing

*Work in progress draft:*

- Test on your distribution of choice.
- Test on a clean machine.
- Ask /r/linux_gaming and GamingOnLinux for help.

## Professionals on the subject

- [Na'Tosha's Bard talk "Developing Unity Games for SteamOS/Linux"][natosha_bard]
- [itch.io documentation page "Distributing Linux builds"][itch_linux]
- [Ethan Lee's talk "Linux/SteamOS Game Development"][flibitijibibo_video] and [slides from it][flibitijibibo_slides]
- [Ethan Lee's text on packaging Linux games][flibitijibibo_text]

[professionals]: https://github.com/hardpenguin/linux_porting_people
[address]: hardpenguin13@gmail.com
[twitter]: http://twitter.com/hardpenguin13

[ubuntu]: https://www.ubuntu.com/
[gol_stats]: https://www.gamingonlinux.com/users/statistics
[steam_stats]: http://store.steampowered.com/hwsurvey/?platform=linux
[so_stats]: https://stackoverflow.com/research/developer-survey-2016#technology-desktop-operating-system
[canonical]: https://www.canonical.com/
[steam_supported]: http://store.steampowered.com/about/
[gog_supported]: https://support.gog.com/hc/en-us/articles/212456929-General-questions
[unity_supported]: https://blogs.unity3d.com/2015/07/01/the-state-of-unity-on-linux/
[unreal_supported]: https://wiki.unrealengine.com/Linux_Support
[distrowatch]: http://distrowatch.com

[natosha_bard]: https://www.youtube.com/watch?v=WYdOQ_k6YvI
[itch_linux]: https://itch.io/docs/itch/integrating/platforms/linux.html
[flibitijibibo_video]: https://www.youtube.com/watch?v=B83CWUh0Log
[flibitijibibo_slides]: http://www.flibitijibibo.com/magfest2016/
[flibitijibibo_text]: https://gist.github.com/flibitijibibo/b67910842ab95bb3decdf89d1502de88