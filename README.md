Profiles
========

Forked from https://github.com/volatilityfoundation/profiles

Volatility profiles for Linux and Mac OS X

Each of these profiles is implemented as a zip file. You can enable them individually with your Volatility installation by copying Linux profiles to volatility/plugins/overlays/linux and Mac profiles to volatility/plugins/overlays/mac. 

NOTE: Only enable the profiles you plan to use. If you copy all zip files into the aforementioned directories, Volatility will be extremely slow to load. 

WARNING: These profiles may not be fully tested (or tested at all). Use at your own risk. If you encounter problems, please report them through the issue tracker: https://github.com/volatilityfoundation/profiles/issues. 

Volatility ProfileScan
======================

Forked from https://github.com/volatilityfoundation/profiles

First approach at determining any information about the OS lying into a memory
dump. Based on simple occurences counting, but quite accurate.

Useful for choosing a profile for analysis in Volatility after.

The same things can be done with grep, which may be way faster (but less
accurate). But I wanted something architecture independant and which fits into
Volatility.

Problems right now:
* It the user runs a VM, detection might return the VM's OS.
* Quite slow
* Few informations (mac_get_profile only works with Mavericks?)

## How to use it ?

Simply drop it into your volatility plugins directory, and run the following
command:

```console
p1kachu@GreenLabOfGazon:profilescan$ volatility -f [dump] profilescan
```

You can get some more informations by specifying the `-v` command line parameter.
