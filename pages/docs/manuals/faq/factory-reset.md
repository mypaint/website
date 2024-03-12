+++
title = "How do I reset all settings to the installation defaults?"
summary = " "
+++

MyPaint stores its settings in simple files in a settings folder, which resides
in either your home directory or your user profile area.

You can reset MyPaint to its initial state by removing some or all of these files:
Either delete the entire settings folder or just the relevant file found in the
settings folder.

{{% colour "red" %}}**Deleting the entire folder may also remove any custom brushes,
so be careful.**{{% /colour %}}

# Settings folders
## Linux
- `$HOME/.config/mypaint` - main config area (newer MyPaint versions)
- `$HOME/.local/share/mypaint` - data files such as brushes and backgrounds (newer MyPaint versions)
- `$HOME/.mypaint` - older MyPaint versions shove everything in one folder

## Windows
- `%LocalAppData%\mypaint` - newer versions of MyPaint and Windows
- `C:\Documents and Settings\YOURUSERNAME\.mypaint` - older MyPaint revisions, and older Windows

# Settings files
Some of the files in the settings folder:
- `settings.json` contains all the main UI settings in newer versions of MyPaint.
- `brushes/order\*.conf` stores your brush groups' order.
- `settings.conf` stores settings for older versions of MyPaint.
- `windowpos.conf` stores window position in ancient versions of MyPaint.
