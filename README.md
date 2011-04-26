Flameeyes's scan2pdf
====================

This is a simple script that works as a frontend to scanimage(1) from
the SANE project[1], to scan a number of pages from a compatible
device into one or more PDF documents.

Prerequisites
-------------

 - sane-backends[1] >= 1.0.22 (for scanimage -A)
 - posix-spawn[2] (tested with 0.3.6)
 - libtiff utilities
 - netpbm
 - ImageMagick or GraphicsMagick
 - unpaper

[1] http://www.sane-project.org/
[2] https://github.com/rtomayko/posix-spawn/
