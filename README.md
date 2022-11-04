SubRenamer
==========

A simple script to change all srt filenames accordly to
the video files in the same directory.

```command
$ subrenamer -h
SubRenamer v0.5
A script to change sub filenames accordingly to video files 
in the same directory

Usage: subrenamer [OPTION]

Options:
-a|auto          Automatic mode (no user input)
-w|wait          Wait for user input on closing.
-h|help          Display this help message.
-v|version       Display the version of SubRenamer and exit.
```

------------------------------------------------------------

## Installation

Just copy the script to any folder in your `$PATH`.

Alternatively:

```command
$ git clone https://github.com/polirritmico/subrenamer.git
$ cd subrenamer
$ make install
```
This will copy the script into `$HOME/.local/bin`

## Usage

In the folder with the sub and video files (srt and video
files count must match):

```command
$ subrenamer
```
Press `y` when asked to confirm.


------------------------------------------------------------


## Right click menu Dolphin (KDE) integration

Create this file:

`$XDG_DATA_HOME/kservices5/ServiceMenus/subrenamer.desktop`

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

Now go to `Configure Dolphin` → `Context Menu` and enable `Rename
subtitle`.

