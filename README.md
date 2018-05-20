# odrobian
Save of Odroid Odrobian repository from WayBackMachine

Disclaimer - Please note I won't be updating or maintaining this repository, if you want that then please feel free to fork, or create your own. I won't be able to answer any questions either, as I'm neither the maintainer, nor an expert on any of this.

# Why revive the Odrobian repository ?

I have two Odroid C1 boards, recently went to update software and discovered Odroid had deleted the Odrobian repository, presumably because C1 is now "old" and they don't want to support it anymore. It appears also that the Odrobian package maintainer has "disappeared", which is sad as it's a good project.

I, and I imagine some others may want to use this software, so I have retrieved as best I can the latest files from WayBackMachine (archive.org) and uploaded them here. ( Using https://github.com/hartator/wayback-machine-downloader , along with some hours of filling in gaps with manual wget commands and a nice wayback-downloader script that uses wget - https://gist.github.com/lazanet/872f88c9874e4a7a78fd )

Of particular use is the OS images, and the "oh-utils", and the documentation. Oh-utils can be used to control CPU speed, infra-red, zram and some other stuff.

More info on Odrobian - https://forum.odroid.com/viewtopic.php?t=18771

# Odrobian OS Images

Due to github filesize limits, some images have been split into a .rar container, and you will therefore need to use rar software in order to obtain the orginal .xz file. ( rar and unrar packages are available free from the Debian repository )

Refer to the ./images folder for Odrobian images

# apt sources

You'll need to update your apt sources if you want to use this github repository for deb packages hosted here (apt-get update, apt-get install). If you want to upgrade from Jessie -> Stretch , then the "[trusted=yes]" is required (something to do with SHA1 being removed in apt in Stretch). You can also change http to https (if you want), but do ensure apt-transport-https is installed first.

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

# Where to now ?

Armbian will run on Odroid C1, so that could be worth checking out ... Have fun ...

# Thanks

Thanks to github for (hopefully) allowing this repository to be hosted here. Apologies for the large files, but - 1. they are static so should only have to stored once, and 2. they are unlikely to be downloaded all that often, so shouldn't be a bandwidth consideration.

And, of course, thanks to the original maintainer XeoSal and helpers on Odroid forum, for providing Odrobian for us.
