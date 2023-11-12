Re: DVD-RW not working in Linux Mint

Post by Lord Boltar » Thu Sep 27, 2018 11:04 am
there are a few files to check to see if they are installed

open synaptic package manager and search for the following

libdvd-pkg

libdvdnav4

dvd+rw-tools

libburn4

libdvdread4

libdvdcss2

if not there you can install then

Hope this helps





-----------




John_B	
    Level 2
    Level 2	
    Posts: 76	
    Joined: Sun Jun 01, 2014 12:16 pm	
    Location: Earth

Re: CD Mounting Issue

Post by John_B » Sat Aug 20, 2022 8:39 pm
Linux Mint 20 Combined command to install brasero etc:

sudo apt install brasero brasero-cdrkit gir1.2-brasero-3.1 cdrdao cue2toc udftools rhythmbox-plugin-cdrecorder vcdimager dvd+rw-tools udfclient cdrkit-doc tracker libosinfo-l10n icedax vorbis-tools cdrskin xorriso xorriso-tcltk cdck

brasero

Brasero is a simple application to burn, copy and erase CD and DVD
media: audio, video or data. It features among other things:
* On-the-fly burning
* Multisession support
* On-the-fly conversion of music playlists in all formats supported by
GStreamer

This package contains the main binary, the burning plugins and the
nautilus extension.

The following packages, if installed, will provide Brasero with added
functionality:
* cdrdao to burn combined data/audio CDs and for byte-to-byte copy
* GStreamer backends to support more audio formats
* vcdimager to create VCDs or SVCDs
* libdvdcss2 to copy encrypted DVDs

sudo apt install brasero

--

brasero-cdrkit

This package contains extensions for Brasero, based on the genisoimage,
growisofs, wodim, readom and dvdauthor programs. They are only needed
for the following operations in Brasero:
* Audio CD burning with CD-Text information
* Video DVD creation

sudo apt install brasero-cdrkit

--

(Optional)

gir1.2-brasero-3.1

This package contains introspection data for the GNOME CD/DVD burning library

It can be used by packages using the GIRepository format to generate
dynamic bindings.

sudo apt-get install gir1.2-brasero-3.1

--

cdrdao

cdrdao records audio or data CD-Rs in disk-at-once (DAO) mode based on a
textual description of the CD contents.

Recording in disk-at-once mode writes the complete disc, i.e. lead-in, one or
more tracks and lead-out, in a single step. The commonly used track-at-once
(TAO) mode writes each track independently which requires link blocks between
two tracks. You probably want to use this if you're copying a CD with multiple
tracks, like most audio CDs.

cdrdao can also handle the bin/cue format commonly used for VCDs or disks with
subchannel data.

If you just want to burn a normal data CD, you probably want wodim instead.

sudo apt install cdrdao

--

cue2toc

CUE files are text files describing the layout of a CD-ROM and typically carry
the extension ".cue". cdrdao and cdrecord, the two CD recording programs for
Linux systems, cannot read these files. This program converts CUE files into
the TOC format that cdrdao can understand.

It also features automatic data format conversion (e.g., MP3 to WAV) before
burning; the exact action taken is determined by the file extensions and the
user's configuration.

sudo apt install cue2toc

--

udftools

This package contains a number of user-space tools related to
creating filesystems in the UDF (Universal Disk Format), which is
primarily used for DVDs, but sometimes also CD-ROMs and HDDs:

mkudffs - Format a device, creating an empty UDF filesystem
udflabel - show or change UDF filesystem label
udfinfo - show information about UDF filesystem
wrudf - Maintains a UDF filesystem
cdrwtool - Low-level drive management (e.g. set writing speed, format)
pktsetup - Set up a packet writing device (/dev/pktcdvd0) for a drive

sudo apt install udftools

--

rhythmbox-plugin-cdrecorder

Rhythmbox is a very easy to use music playing and management program
which supports a wide range of audio formats (including mp3 and ogg).
Originally inspired by Apple's iTunes, the current version also supports
Internet Radio, iPod integration and generic portable audio player
support, Audio CD burning, Audio CD playback, music sharing, and
Podcasts.

This package contains the brasero based CD/DVD burning plugin.

sudo apt install rhythmbox-plugin-cdrecorder

--

vcdimager

This package contains a collection of tools to master (Super)VideoCD,
either directly from compliant MPEG streams with no PlayBack Control
(PBC), or out of an XML description for a full-featured (S)VCD.

This package also contains a VideoCD ripping tool to rip mpeg streams
from VideoCD images, and some debugging tools.

sudo apt install vcdimager

--

dvd+rw-tools

The dvd+rw-tools suite makes it possible to burn DVD images created by
dvdauthor or genisoimage to DVD+R, DVD+RW, DVD-R, and DVD-RW disks,
replacing cdrecord-proDVD in many cases.

This package contains dvd+rw-mediainfo (to give details about DVD
disks), and some programs to control the write speed and obtain
information from DVD-RAM.

Additionally, it depends on the growisofs package to provide the main
front-end for burning DVD-like media.

sudo apt install dvd+rw-tools

--

udfclient

UDFclient is a userland implementation of the UDF filesystem as defined by the
OSTA group. UDFclient is designed to be a study platform and a run-up to a full
read and write kernel level implementation.

Except udfclient it contains additional utilities:

cd_disect - Display report of disc
cd_sessions - Show sessions on disc
mmc_format - Format optical disc
newfs_udf - Create UDF filesystem on file or a formatted disc
udfclient - FTP-like client for UDF filesystem
udfdump - Dump information from UDF filesystem

sudo apt install udfclient

--

cdrkit-doc

This is the documentation for the cdrkit package suite, namely
wodim, genisoimage and icedax.

sudo apt install cdrkit-doc

--

tracker

Tracker is an advanced framework for first class objects with associated
metadata and tags. It provides a one stop solution for all metadata, tags,
shared object databases, search tools and indexing.

sudo apt install tracker

--

libosinfo-l10n

libosinfo is a GObject based library API for managing information about
operating systems, hypervisors and the (virtual) hardware devices they
can support. It includes a database containing device metadata and
provides APIs to match/identify optimal devices for deploying an
operating system on a hypervisor.

This package contains the libosinfo translations.

sudo apt install libosinfo-l10n

--

icedax

icedax lets you digitally copy ("rip") audio tracks from a CD, avoiding
the distortion that is introduced when recording via a sound card. Data
can be dumped into raw (cdr), wav or sun format sound files. Options control
the recording format (stereo/mono; 8/16 bits; sampling rate, etc).

Please install cdrkit-doc if you want most of the documentation and
README files.

sudo apt install icedax

--

vorbis-tools

vorbis-tools contains oggenc (an encoder), ogg123 (a playback tool),
ogginfo (displays ogg information), oggdec (decodes ogg files), vcut
(ogg file splitter), and vorbiscomment (ogg comment editor).

ogg123 can play both Ogg Vorbis and FLAC audio streams.

sudo apt install vorbis-tools

--

cdrskin

provided by cdrecord. It writes data sessions to CD, DVD, or BD media.
To CD media it may also write audio sessions.
Multi-session is possible on all media types except DVD-R DL and
fastly blanked DVD-RW.

This is a burner-only application. If you want a burner and ISO 9660 image
manipulation application, please install the xorriso package.

sudo apt install cdrskin

--

xorriso

xorriso is a command line and dialog application, which creates, loads,
manipulates, and writes ISO-9660 file system images with Rock Ridge
extensions.

It maps file objects from POSIX compliant file systems into Rock Ridge
enhanced ISO-9660 file systems and features session-wise manipulation
of such file systems. It can load the management information of existing
ISO images and write the resulting session to optical medium or as
file system objects.

Supported optical media types:
- CD-R, CD-RW
- DVD-R, DVD-R DL, DVD-RW, DVD+R, DVD+R DL, DVD+RW, DVD-RAM
- BD-R, BD-RE

Some interesting features:
- Emulation of the mkisofs and cdrecord programs.
- Data backup and restore capabilities - compression, ACLs, and filters.
- Isohybrid MBR with partition offset - features booting ISOLINUX from
USB sticks, or from other devices that appear to PC-BIOS as hard disks.
The images carry a conventional partition table for a USB stick;
the first partition reports the size of the ISO image, but starts at a
non-zero address. It is nevertheless still mountable.
- Jigdo Template Export - jigdo representation of the resulting ISO-9660
image, generated on the fly.

Test suite:
xorriso source code comes with a release engineering test-suite called
`releng', which aims to cover most of the functionality of the xorriso
and the underlying libraries of libburn, libisofs, and libisoburn.

sudo apt install xorriso

--

xorriso-tcltk

xorriso is a command line and dialog application, which creates, loads,
manipulates, and writes ISO-9660 file system images with Rock Ridge
extensions.

xorriso-tcltk offers the most important features in a single GUI window
together with help texts and references to xorriso's man page.
The xorriso commands which get triggered by GUI components are shown in a
scrollable text field or optionally may get logged to a file.
Click on any GUI component by the rightmost mouse button to see the
component's help text.

sudo apt install xorriso-tcltk

--

cdck

cdck (CD/DVD check tool) is a simple console program to verify CD/DVD
quality. The known fact is that even if all files on the disc are readable,
some sectors having bad timing can easily turn into unreadable ones in the
future.

To get an idea about a disc cdck reads it sector by sector, keeping all
reading timings and then tells you its verdict. Optionally it can write the
timing table into text file usable by gnuplot(1) program, so you can draw
some graphs out of it.

sudo apt install cdck

========

BE SURE TO TYPE y FOR YES

libdvd-pkg

This package provides libraries that are needed for playing video DVDs
with a media player (such as VLC, SMplayer, Totem, etc.). It automates
the process of downloading source files, compiling them, and installing
the binary packages.

sudo apt install libdvd-pkg

sudo dpkg-reconfigure libdvd-pkg

July 25, 2019
How to Play DVD in Ubuntu 18.04, 16.04 and 14.04 - It's FOSS
https://itsfoss.com/play-dvd-ubuntu-1310/

========
LM 21 Cinnamon | Dell Latitude E4310 (A15) | Core i5 560m | Mobile Intel QS57 Express | 8 GB RAM | CT2000MX500SSD1 | ST2000LM003 HN-M201RAD in an S251SMU33EP | Intel AC 7260 | ECUSB3S11 (NEC / Renasis 720202) 34mm ExpressCard
Top
