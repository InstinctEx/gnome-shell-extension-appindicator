# ARCHIVED 

The issue has been fixed

# Why did I fork?
Recently there has been a huge bug in this extension causing many people suffering when joining a Discord Voice chat while using specific icon packs.I fixed it, no more 100% cpu usage!
Thanks to scj643, this is  an updated fork based on his!

# AppIndicator/KStatusNotifierItem support for GNOME Shell
This extension integrates Ubuntu AppIndicators and KStatusNotifierItems (KDE's blessed successor of the systray) into GNOME Shell.

[<img alt="" height="100" src="https://raw.githubusercontent.com/andyholmes/gnome-shell-extensions-badge/master/get-it-on-ego.svg?sanitize=true">](https://extensions.gnome.org/extension/615/appindicator-support/)

## Features
* Show indicator icons in the panel.
* Reveal indicator menus upon click.
* Double clicking an icon will activate the application window (if implemented by the indicator).
* Middle mouse click an icon to send a 'SecondaryActivate' event to the application. Support needs to be implemented in the application. [Info 1](https://bugs.launchpad.net/unity/+bug/812933), [Info 2](https://developer.ubuntu.com/api/devel/ubuntu-13.10/c/AppIndicator3-0.1.html).

## Missing features
* Tooltips: Not implemented in `libappindicator` nor in Unity and I've yet to see any indicator using it for anything relevant (KDE ones maybe?). Also, the GNOME designers decided not to have tooltips in the shell and I'd like to honor that decision.

## Known issues
* ClassicMenu Indicator takes ages to load and has been reported to freeze the shell forever. This is probably caused by the insane amount of embedded PNG icons. Try at your own risk.

## Installation
Normal users are recommended to get the extension from [extensions.gnome.org](https://extensions.gnome.org/extension/615/appindicator-support/).

Alternatively, you can check out a version from git and symlink
`~/.local/share/gnome-shell/extensions/appindicatorsupport@rgcjonas.gmail.com` to your clone:

```
ln -s $PWD ~/.local/share/gnome-shell/extensions/appindicatorsupport@rgcjonas.gmail.com
gnome-extensions enable appindicatorsupport@rgcjonas.gmail.com
```

You may need to restart GNOME Shell (<kbd>Alt</kbd>+<kbd>F2</kbd>, <kbd>r</kbd>, <kbd>⏎</kbd>)
after that.

## Guidelines for bug reports
Unfortunately, this extension is not completely bug free and will probably never be.
In order to successfully resolve remaining issues, you need to provide some data:

* Your distribution, Shell version and extension version (something like "latest git" or "latest from extensions.gnome.org" is sufficient).
* The indicator that caused the bug (if applicable).
* Instructions how to reproduce it. **This is the single most important point**. Bugs which [cannot be reproduced](http://xkcd.com/583/) cannot be fixed.

Bug reports which do not provide the necessary information may be closed as "invalid" without prior notice.

## Release process
This section serves as reminder for the current maintainer and as instruction set for an eventual sucessor.

* The maintainer decides when to release a new version.
* Versions are tagged (and signed). Version numbers sould be kept in sync with the versions submitted to `extensions.gnome.org`.
  This implies that version numbers are integers which will be incremented with each release.
* The maintainer will tag a new version and generate a zip file using `make`.
* The zip file will be tested to ensure that nothing was missed when packaging it.
* Only if it passed, it is uploaded to `extensions.gnome.org` and the tag is pushed.

This release process has been in place since v9.
