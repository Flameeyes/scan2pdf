Flameeyes's scan2pdf
====================

This is a simple script that works as a frontend to `scanimage(1)`
from the SANE project, to scan a number of pages from a compatible
device into one or more PDF documents.

Prerequisites
-------------

 - [sane-backends](http://www.sane-project.org/) (>= 1.0.22
   recommended, for `scanimage -A`)
 - [posix-spawn](https://github.com/rtomayko/posix-spawn/) (tested with 0.3.6)
 - libtiff utilities
 - netpbm (a note for Gentoo users: you need both `tiff` and `jpeg`
   USE flags enabled for the pnm2tiff utility.)
 - ImageMagick or GraphicsMagick
 - [unpaper](https://flameeyes.com/p/unpaper)
 - [inifile](https://rubygems.org/gems/inifile) (>= 2, optional, for
   configuration file support.)

The configuration file
----------------------

Some device always require the same parameters to be passed, because
they are either center-based scanning, or ADF-only. Some other time
you might want for them to use a different resolution by default, or
not to use unpaper.

In these cases you can configure `scan2pdf` to provide those
options. The configuration file is a key-value pair file (`.ini` file)
and it resides in `${XDG_CONFIG_HOME}/eu.flameeyes.scan2pdf` (which by
default on Linux system is `~/.config/eu.flameeyes.scan2pdf`).

The configuration file uses a `[defaults]` section, which only has one
key (`device`), and then one section for device. Note that device name
is not matched against the names reported by `scanimage`, but rather
against the value of the `--device` option passed to `scan2pdf`. It is
suggested to provide a default device when using the configuration
file.

The key names within the device sections are the same as the
parameters passed to `scan2pdf` without the two leading dashes.
