# Installation on Archlinux/Manjaro systems  

I have no idea why, but this version no longer works when compiling directly into ArchLinux. Service 'vpnagentd' does not work.  

I've edited the [fork I got from @ariel-miculas](https://github.com/elppans/cisco-secureclient/tree/secureclient) to:  

1) "Comment" the lines I had added (old glib2, icu and libxml2) and also the workaround I did at the end of PKGBUILD.  

2) Update the Cisco Secureclient version to "5.1.3.62"  

On Archlinux I finally managed to get the "vpnagentd" service to work... But that's it... The app didn't open.  
In Manjaro everything worked 100% and I even completely removed the ArchLinux application, copied the version I compiled in Manjaro and installed it on ArchLinux... It also worked 100%  

Tested systems:  

```
manjaro-kde-23.1.4-240406-linux66 (Fully updated 24.05.05):  
Linux manjaro-vm 6.6.26-1-MANJARO #1 SMP PREEMPT_DYNAMIC Wed Apr 10 20:11:08 UTC 2024 x86_64 GNU/Linux  
```

```
archlinux-2024.02.01-x86_64 (Fully updated 24.05.05):  
Linux archlinux 6.8.9-arch1-1 #1 SMP PREEMPT_DYNAMIC Thu, 02 May 2024 17:49:46 +0000 x86_64 GNU/Linux  
```

Images of the tests in order:  

1) [IMG Info Arch/Manjaro](https://i.imgur.com/Kfu8tQ4.png)  
2) [IMG SystemD Arch/Manjaro](https://i.imgur.com/d4xk1dz.png)  
3) [IMG Test Arch](https://i.imgur.com/UMNb94Y.png)  
4) [IMG Test Manjaro](https://i.imgur.com/txhsw3t.png)  
5) [IMG Test App version Manjaro in ArchLinux](https://i.imgur.com/lc5IOus.png)  

- Observation:  

```
For this version of Cisco (5.1.3.62), it was **NOT** necessary to do workarounds such as adding libxml2 2.11.5-1 or configuring variables.  
I just compiled it and it worked.  
```

## Installation on Debian/Ubuntu systems with [makedeb](https://github.com/elppans/makedeb)  

Adaptation for PKGBUILD installation to cisco-secureclient installation using Ubuntu 22.04.4 and makedeb application has been made.  

To install using this adaptation, rename the original **PKGBUILD** file to any other name, and then rename the `PKGBUILD.makedeb` file to **PKGBUILD**.  
After that, to compile and install just do the command:  

```
makedeb -si
```

Another **PKGBUILD** has also been adapted to make an installation using the `.zst` package already compiled in Manjaro.  
The file name is `PKGBUILD.MJR_bin_makedeb`.  
To install with the binary package, just do the same as in the previous example.  
