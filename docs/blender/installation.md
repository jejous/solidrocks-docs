# Installation

## Install

1. Download the SolidRocks `.zip` file. **Do not unzip it.**
2. In Blender, open **Edit > Preferences > Add-ons**.
3. Click the arrow at the top right and choose **Install from Disk...**, then select the `.zip` file.
4. Tick the checkbox next to **SolidRocks for Cycles** to enable it.

!!! note "Check this step against the actual install"
    Menu names above are for Blender 5.1. *(Author: verify with the final build and add a screenshot.)*

## Where to find it

- **Render Properties** tab: the full SolidRocks panel.
- **3D Viewport**, sidebar (press **N**), **SolidRocks** tab: the same panel.

## Presets

The Studio, Interior and Exterior presets are installed with the add-on. By default they are stored in Blender's user configuration folder. You can choose another folder in the add-on preferences (**Presets Folder**), for example a folder shared by a team.

## Update (or Lite to Pro)

1. Install the new `.zip` the same way (**Install from Disk**), over the current version. No need to uninstall first.
2. **Untick, then tick again** the SolidRocks checkbox in the add-on list (or restart Blender). Until then, Blender keeps running the previous version.

Your presets folder and your add-on preferences are kept.

!!! warning
    Never keep two SolidRocks installations at the same time (for example an old single `.py` file and a `.zip` install). Uninstall the old one first.

## Uninstall

Remove the add-on from **Edit > Preferences > Add-ons**.

Your files are safe: a scene saved while SolidRocks is ON is written with **your original settings**. Without the add-on, it simply renders with them.
