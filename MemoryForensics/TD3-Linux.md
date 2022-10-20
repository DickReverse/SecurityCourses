Good resource on the matter : https://stuxnet999.github.io/dfir/2020/09/20/Linux-Memory-Forensics.html

# Memory collection with AVML
AVML is published by Microsoft and is very easy to use : 
- [https://github.com/microsoft/avml](https://github.com/microsoft/avml).

## Setup 

Download the latest release, example : 
- https://github.com/microsoft/avml/releases/tag/v0.9.0

Execute the following code, with a root shell, in the Linux machine you want to dump memory from : 
```
./avml mem.lime
```

Output will be in LIME format.
## Building the profile
-Before creating your own profile (Volatility 2) or symbol table (Volatility 3), try to find in the shared ones:
    -   [Volatility 2 Profiles](https://github.com/volatilityfoundation/profiles/)
    -   [Volatility 3 Profiles](https://github.com/volatilityfoundation/volatility3#symbol-tables)

-   Go to `tools/linux` in Volatility directory and run `make` command:

```
sudo apt install linux-image-$(uname -r) linux-headers-$(uname -r)
cd tools/linux/
make
```

-   -   If you get `ERROR: modpost: missing MODULE_LICENSE()` error in `make` command, follow the solution below:
        -   The solution is simply to add `MODULE_LICENSE("GPL");` as last line in `volatility/tools/linux/module.c`
    -   If you get `bin/sh: 1: dwarfdump: not found` error in `make` command, install the `dwarfdump` package.
        -   `sudo apt install dwarfdump`

-   You should see a new `module.dwarf` file. You also need the `System.map` file in the `/boot` directory as it contains all symbols related to the currently running kernel.

In case you need to build the profile, you have to save module.dwarf and System.map files : 
```
zip $(lsb_release -i -s)_$(uname -r)_profile.zip ./volatility/tools/linux/module.dwarf /boot/System.map-$(uname -r)
```

You need to build the profile of the machine you want to analyze.
Best instructions : https://github.com/volatilityfoundation/volatility/wiki/Linux 

Copy it back, with the .lime file, to the box you want to analyse from.
In general, we don't do analysis on the same box. Since this is a lab, it is allowed.


# Memory analysis

## Install the profile 

Copy the profile to the right volatility directory :
```
mv profile.zip /usr/share/volatility/volatility/plugins/overlays/linux
```

Make sure your new profile is installed, and determine its full name :
```
volatility --info | grep [Distribution]
```

A few commands to run : 
![[Pasted image 20221020225045.png]]
