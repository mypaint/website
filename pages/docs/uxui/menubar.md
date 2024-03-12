+++
title = "Menubar"
summary = "Description of MyPaint's menubar"
mypaintver = "v3.0.0"
+++

# Patterns
Suffix "..." opens the file selector.

# File
## Description
Operations that:
- Read or write data to the system.
- Modify the parts of the [working file]({{< ref "concepts#working-file" >}}).
- Change the running state of MyPaint

## Items
- **New**: {{% colour "yellow" %}}Create a new document and set it as the working file{{% /colour %}}
- **Open...**: Open the file browser and attempt to load the user-specified path.
- **Open Recent**: [Rollover menu]({{< ref "../hig/menus#rollover" >}}), displays up to {{% colour "yellow" %}}n{{% /colour %}} no. of items previously opened in MyPaint.
    - \> **List of recent files**: Attempt to load this path.
- Revert

---

- **Save**: If the working file is preexisting, overwrite the file with the working file. Otherwise, *Save As...*
- **Save As...**: Open the file browser and saves the file with the [default][pref-load-save] image format (unless specified otherwise) in a user-specified path. The working file will now save to that path in future save operations.
- **Export...**: *Save As...*, but the working file will not automatically save to the specified path in future save operations.

---

- **Save as [Scrap][con-scrap]** Saves the current file in the [scraps directory][pref-load-save].
- Open Next Scrap
- Open Previous Scrap

---
- {{% colour "yellow" %}}**Frame Enabled**{{% /colour %}}: [Checkbox][hig-checkbox], toggles the [canvas frame][con-frame]
    - Warning: This makes more sense in [view][menu-view], but only after [this issue is fixed](https://github.com/mypaint/mypaint/issues/1227)
- {{% colour "red" %}}**Symmetrical Painting Active**{{% /colour %}}: [Checkbox][hig-checkbox], toggles [symmetry][con-symmetry]
    - Warning: This makes more sense in [view][menu-view].

[menu-view]: #View
[con-frame]: {{< ref "concepts#frame" >}}
[con-scrap]: {{< ref "concepts#scraps" >}}
[con-symmetry]: {{< ref "concepts#symmetry" >}}
[pref-load-save]: {{< ref "preferences#load-&-save" >}}
[hig-checkbox]: {{< ref "../hig/activators#checkbox" >}}
