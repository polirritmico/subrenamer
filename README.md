SubRenamer
==========

A simple script to change all srt filenames accordly to
the video files in the directory.

```command
foo@bar $ subrenamer -h
SubRenamer v0.5
A script to change sub filenames accordingly to video files

Usage: subrenamer [OPTION]... [FILE]
subrenamer [OPTION]... [FILE] [OUTFILE]

Options:
-a|auto          Automatic mode (no user input)
-w|wait          Wait for user input on closing.
-h|help          Display this help message.
-v|version       Display the version of SubRenamer and exit.
```

------------------------------------------------------------

## Installation

```command
$ git clone https://github.com/polirritmico/subrenamer.git
$ cd subrenamer
subrenamer $ make install
```

## Run

In the folder with the sub and video files (srt and video
count must match):

```command
$ subrenamer
```
Press `y` when asked to confirm.

------------------------------------------------------------

## Right click menu Dolphin (KDE) integration

Create this file: `$XDG_DATA_HOME/kservices5/ServiceMenus/subrenamer.desktop` with this content:

```desktop
[Desktop Entry]
Type=Service
Icon=video-x-generic
X-KDE-ServiceTypes=KonqPopupMenu/Plugin
MimeType=application/x-subrip;
Actions=renamesub;
Encoding=UTF-8

[Desktop Action renanesub]
Name=Rename subtitle
Icon=video-x-generic
Exec=konsole --workdir %d -e subrenamer -a -w
```

Now go to `"Configure Dolphin" → "Context Menu"` and enable `Rename
subtitle`.

