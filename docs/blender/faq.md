# FAQ & known pitfalls

## Persistent Data

Persistent Data keeps the scene in memory between renders. It is faster for repeated renders, but **Blender can then ignore some setting changes** between two renders (World Sampling at least). Two consequences:

- **Comparing two settings by hand?** Switch Persistent off first, otherwise both renders may use the same settings without warning.
- **Guess and Calibrate** switch it off themselves while they measure, and restore it after.

## Guess or Calibrate is very slow

- **Antivirus**: some antivirus software (Avira, in our tests) slows these tools a lot, because they write and read back a small image after each test render. Excluding Blender's temporary folder, or pausing the antivirus during the measurement, helps.
- Complex scenes (volumes, deep subsurface scattering) are slow to measure by nature.
- More test zones = longer runs.

## The "modified" mark appears next to my preset

The scene's values no longer match the preset file: you edited a value, or the file was changed after the scene was saved. Reload the preset to go back to the file, or save your values as a new preset.

## The Region button is red

Blender's own render border (Ctrl+B) no longer matches the SolidRocks Region button. Click the button again, or redraw the region, so the measuring tools use the zone you expect.

## Prod in the Preset tab and in Active Settings are different

Normal. The Preset tab shows preset values. Active Settings shows what Cycles really receives after the resolution and denoise adjustments.

## I sent my .blend to someone without SolidRocks

A file saved while SolidRocks is ON contains **your original settings**, not the SolidRocks values. When you reopen it with SolidRocks installed, the SolidRocks values come back automatically.

To send a file that renders **with the SolidRocks values** on a machine or render farm without the add-on, use **Make Permanent** first, then save.

## Old scenes saved with an earlier SolidRocks version

Earlier versions forced some Blender settings (Light Tree off, refractive caustics off, World Sampling None, Classic sampling pattern). Current versions no longer touch them, and no longer restore them either. Check the **Light Tree / Reflect / Refract** buttons and run **Diagnose Scene** on old files.

## Animation

SolidRocks has no special animation mode. For animation:

- Switch **Anim Seed** on, so noise does not stay frozen on screen.
- Be careful with **Persistent** if you use animated Geometry Nodes or complex Shape Keys (known Cycles limitation).
- Low sample counts with the denoiser can flicker from frame to frame. Test a few frames before a long render.

## Which Blender version?

Tested on Blender **5.1.1**. A new Blender version can change Cycles' Python interface; if something breaks after a Blender update, please report it.

## Contact

*(Author: contact address or support page here.)*
