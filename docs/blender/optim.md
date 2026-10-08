# Optim tab

Settings you set once per scene, and the scene check-up.

## Biased Volumes

Blender's own setting. Uses the older, faster "biased" ray marching for volumes. The **Volume step rate** and **Volume max steps** curves of the Preset tab only work when this is on.

## Simplify

Blender's own Simplify settings: **Max Subdivs** and **Tex. Limit** (maximum texture size at render). Useful for heavy scenes and limited GPU memory.

## Texture Cache

Blender's texture cache settings, available from Blender 5.2. Not shown in Blender 5.1.

## Diagnose Scene

Analyzes the scene and suggests render-time optimizations. **It changes nothing on its own.** When a fix is one click away, a button is shown next to the message.

What it checks includes:

- Rendering on CPU while a GPU is available (**Enable GPU**), CUDA while OptiX is available (**Switch to OptiX**).
- Denoiser off (**Enable Denoiser**), compositor denoising on CPU (**Use GPU for Compositor**).
- A viewport left in Rendered shading, which competes with your render (**Switch Viewport to Solid**).
- World Sampling set to None while the World uses an HDRI or sky (**Set World Sampling to Auto**).
- Simplify, oversized textures, very heavy meshes, many lights (suggests testing Light Tree ON and OFF), many objects.
- Orphan data left in the file (**Purge Orphan Data**).
- Duplicate objects that could share one mesh (**Convert to Instance**, checked against the real geometry).

Thresholds (texture size, polygon count, number of lights...) can be changed in the add-on preferences.
