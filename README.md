SubRenamer
==========
![GitHub last commit](https://img.shields.io/github/last-commit/polirritmico/subrenamer)  [![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)


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
Press `y` to confirm.

### Example

In this folder:

```command
$ tree
.
├── sub1.srt
├── sub2.srt
├── subtitle3.srt
├── video1.mp4
├── video2.mp4
└── video3.mp4
```

Run `subrenamer`

```command
$ subrenamer
SubRenamer v0.5
===============
subrenamer: Building the file list... OK
subrenamer: Getting videos from the list... OK
subrenamer: Getting subtitles from the list... OK
subrenamer: The following files will be renamed:
'sub1.srt' to 'video1.srt'
'sub2.srt' to 'video2.srt'
'subtitle3.srt' to 'video3.srt'
Confirm the changes? (y/n) y
subrenamer: Confirmed. Renaming the subtitles... OK
subrenamer: Quiting...
```

And this is the result:

```command
$ tree
.
├── video1.mp4
├── video1.srt
├── video2.mp4
├── video2.srt
├── video3.mp4
└── video3.srt
```


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

[Desktop Action renamesub]
Name=Rename subtitle
Icon=video-x-generic
Exec=konsole --workdir %d -e subrenamer -a -w
```

Now go to `Configure Dolphin` → `Context Menu` and enable `Rename
subtitle`.

