+++
title = "Backup Files and Autosaves"
+++

### Overwrite Backup Copies

MyPaint makes a backup copy with a tilde `~` after its name when you overwrite a file. This is a feature intended to keep your data safe in the event of a power outage when you are overwriting a large file.
There are no plans to add a user-facing toggle to turn this feature off for v1.2.0,
however one may be added early on in the v1.2.x series (see [issue #395](https://github.com/mypaint/mypaint/issues/395) for a user story and request).

### Automated Backups

MyPaint v1.2.0 makes periodic backups as you work, using a very low-priority background task that shouldn't interrupt your painting flow. It uses an internal area on disk for this, so it won't continually overwrite your working file or make clutter in your working folders.

If MyPaint crashes without saving first, just wait a few seconds before starting MyPaint again, and you should see a dialog resembling

[[v1.2-Backup-Files-and-Autosaves-autosave-recovery.png]]

at startup. Click on the backup you want to recover from to select it, then click the _Recover and Save…_ button. If the recovery succeeds, you will be asked to save the recovered work to disk with a normal dialog just like the one you get with _File → Save_.

If the recovery fails, you will be given the change to visit the internal area where these things are stored using a file browser (Nautilus, Thunar, Windows Explorer…).

[[v1.2-Backup-Files-and-Autosaves-autosave-recovery-failed.png]]

It's rare for this to happen, and we'd expect the normal cause to be hardware failure or a power outage. Even in this case, you'll hopefully be able to recover some layers manually.

If you decide that you don't want MyPaint spinning up your disk every so often write out data, you can adjust the autosave backup interval or just turn it off completely in the preferences. You'll find the setting in _Edit → Edit Preferences → Load and Save → Automated Backups_. We strongly recommend that you keep this setting turned on, however!

[[v1.2-Preferences-load-and-save.png]]

Note that the toggle does not turn off _overwrite_ backups, as described above.
