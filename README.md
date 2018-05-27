# odrobian
Save of Odroid Odrobian repository from WayBackMachine

Disclaimer - I won't be updating or maintaining this repository, if you want that then please feel free to fork, or create your own. I won't be able to answer any questions either, as I'm neither the maintainer or creator, nor an expert on any of this.

# Why rescue the Odrobian repository ?

I have two Odroid C1 boards, recently went to update software and discovered Odroid had deleted the Odrobian repository. It seems that the Odrobian package maintainer has "disappeared", which is sad as it's a good project. So ...

I, and I imagine some others may (still) want to use this software, so I have retrieved as best I can the latest files from WayBackMachine (archive.org) and uploaded them here. ( Using https://github.com/hartator/wayback-machine-downloader , along with some hours of filling in gaps with manual wget commands and a nice wayback-downloader script that uses wget - https://gist.github.com/lazanet/872f88c9874e4a7a78fd )

Of particular use is the OS images, and the "oh-utils", and the documentation. Oh-utils can be used to control CPU speed, infra-red, zram and some other stuff. And, there's quite a lot of packages and enhancements for Debian on Odroid.

More info on Odrobian - https://forum.odroid.com/viewtopic.php?t=18771

# Odrobian OS Images

Due to github filesize limits, some images have been split into a multiple .rar files, and you will therefore need to use rar software in order to extract the orginal .xz file. ( rar and unrar packages are available free from the Debian repository using apt-get )

Refer to the ./images folder for Odrobian images

# apt sources

You'll need to update your apt sources if you want to use this github repository for deb packages hosted here (apt-get update, apt-get install).

If you want to upgrade from Jessie -> Stretch , then the "[trusted=yes]" is required (something to do with SHA1 being removed in apt in Stretch - https://unix.stackexchange.com/questions/387053/debian-9-apt-and-gpg-error-inrelease-the-following-signatures-were-inva/387054#387054 ). See GPG warning below. 

You can also change http to https (if you want), but do ensure apt-transport-https is installed first.

My old /etc/apt/sources.list.d/odrobian-s805.list

```
deb http://oph.mdrjr.net/odrobian/ odroid main s805

deb http://oph.mdrjr.net/odrobian/ jessie main s805
```

My new one :

```
deb [trusted=yes] http://raw.githubusercontent.com/doncharisma/odrobian/master/ odroid main s805

deb [trusted=yes] http://raw.githubusercontent.com/doncharisma/odrobian/master/ jessie main s805
```

( OR, just add them to your /etc/apt/sources.list file )

I wasn't able to get rid of this warning, but I don't think it prevents the repository being used (as it's a warning) :

```
W: GPG error: https://raw.githubusercontent.com/doncharisma/odrobian/master odroid InRelease: The following signatures were invalid: F3230DD84F39A606727D3D5D1B881FD777439C3B
```

*** Please note the files in /sources/*.list are, erm, wrong (because the deb entries point to the old repository), so you may have to manually edit the files after for instance installing "odrobian-platform-s805" ***

# Where to now ?

XeoSal has some Odrobian scripts on Github - https://github.com/XeoSal/odrobian-utility

**Armbian** will run on Odroid C1, so that could be worth checking out ... 

ZRam on Armbian Jessie (Ordriod C1) :
```
wget http://raw.githubusercontent.com/doncharisma/odrobian/master/pool/s805/s/s805-zram/s805-zram_1.0-1_armhf.deb

dpkg -i s805-zram_1.0-1_armhf.deb

# comment out /var/swap line in /etc/fstab

enable-zram
sync
reboot
# to check
free -m
swapon -s
```

( https://forum.odroid.com/viewtopic.php?f=112&t=18226 )

# Thanks

Thanks to github for (hopefully) allowing this repository to be hosted here. Apologies for the large files, but - 1. they are static so should only have to stored once, and 2. they are unlikely to be downloaded all that often, so shouldn't be a bandwidth consideration.

And, of course, thanks to the original maintainer XeoSal and helpers on Odroid forum, for providing Odrobian for us.
