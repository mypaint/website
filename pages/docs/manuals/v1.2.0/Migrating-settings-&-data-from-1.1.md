Starting with **v1.2.0**, some of the configuration files changed location to conform to the [xdg standard](https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html). The instructions on this page describe how to migrate settings from **v1.1** or older.

## Setting up

Open a terminal and start a bash shell (by entering the command `bash`) if you're not sure that the default shell is bash. Then enter the following:

```
DATADIR=${XDG_DATA_HOME:-$HOME/.local/share}/mypaint
CONFDIR=${XDG_CONFIG_HOME:-$HOME/.config}/mypaint
OLDDIR=$HOME/.mypaint
```
---

All items can be migrated independently, although if your old `settings.json` file references an old scratchpad, you will have to manually update the path to the new location of that scratchpad file (if that file is located under the old directory).

Search for "last_opened_scratchpad" to find the path that may need to be updated.

## Copying backgrounds and scratchpads

_You need to first run the commands in **Setting up** in the same terminal_

```
cp -r --backup=simple $OLDDIR/backgrounds $DATADIR
cp -r --backup=simple $OLDDIR/scratchpads $DATADIR
```

## Copying settings and shortcut maps

_You need to first run the commands in **Setting up** in the same terminal_

> :warning:  
> If you have changed the settings in MyPaint >= 1.2.0, migrating old settings will overwrite those changes.  
> There is no _easy_ way to _merge_ settings.

```
cp -r --backup=simple $OLDDIR/settings.json $CONFDIR
cp -r --backup=simple $OLDDIR/accelmap.conf $CONFDIR
```

---

> :information_source:  
> The `--backup=simple` flag will create copies of existing files that would otherwise be overwritten, and append `~` to their names, so that e.g. a pre-existing `settings.json` file will be renamed to `settings.json~`. If there is a problem with the migration, you can rename these backups to their original names to restore them.
