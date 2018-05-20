# odrobian
Save of Odroid Odrobian repository from WayBackMachine

Disclaimer - Please note I won't be updating or maintaining this repository, if you want that then please feel free to fork, or create your own. I won't be able to answer any questions either, as I'm neither the maintainer, or an expert on any of this.

Why ? I have two Odroid C1 boards, recently went to update software and discovered Odroid had deleted this repository, presumably because C1 is now "old" and they don't want to support it anymore. It appears also that the Odrobian package maintainer has "disapeared".

I, and I imagine some others may want to use this software, so I have retrieved as best I can the latest files from WayBackMachine (archive.org) and uploaded them here. ( Using https://github.com/hartator/wayback-machine-downloader )

Of particular use is the OS images, and the "oh-utils", and documents.

More info on Odrobian - https://forum.odroid.com/viewtopic.php?t=18771

# Odrobian OS Images

Due to github filesize limits, some images have been split in a .rar container, and you will therefore need to use rar software in order to obtain the orginal .xz file.

# apt sources

You'll need to update your apt sources if you want to use this github repository for deb packages hosted here. If you want to upgrade from Jessie -> Stretch , then the "[trusted=yes]" is required (something to do with SHA1 being removed in Stretch). You can also change http to https (if you want), but do ensure apt-transport-https is installed first.

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

# Thanks

Thanks to github for (hopefully) allowing this repsository to be hosted here. Appologies for the large files, but - 1. they are static so should only have to stored once, and 2. they are unlikely to be downloaded all that often, so shouldn't be a bandwidth consideration.

And, of course, thanks to the original maintainer and helpers, for providing Odrobian for us.
