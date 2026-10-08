# Create tab

One-click scene content. **Nothing existing is modified or deleted**: each button creates new data next to what you have.

## World

- **HDRI**: a new World from an HDRI image you pick.
- **Sky**: a new World with a procedural sky (no file needed).
- **Color**: a new World with a flat color (black by default).

The previous World stays in the file.

## Camera to View

Creates a new camera matching the current viewport view and makes it the scene camera. An existing camera is never moved.

## Cyclorama

A procedural backdrop (infinite cove), in an **SR_Studio** collection. The trash icon removes it.

## Light Rig

A 3-point light rig (Key, Fill, Rim), in the **SR_Studio** collection. Adjust its **Altitude** and **Rotation**, and each light's power, color and distance, from the **Studio Lights** list. The trash icon removes it.

## Paint Light

Click on a surface to place a light there, then adjust it with the mouse wheel:

| Key | Adjusts |
|---|---|
| **T** | Light type (Area, Point, Spot, Sun) |
| **S** + wheel | Size |
| **D** + wheel | Distance from the surface |
| **F** + wheel | Power |
| **C** + wheel | Color |

!!! note "Author"
    Keys taken from the September version: check them against the final build.

Left-click again to move it. **Right-click** or **Enter** to confirm, **Esc** to cancel. **Move** in the Studio Lights list reopens the tool on an existing light.

## Near / Far attenuation

Available on every light (Light properties, and in the Studio Lights list for SolidRocks lights; not for Sun lights). Cycles has no native near/far falloff: SolidRocks builds it with a small node setup on the light, controlled by **Near** and **Far** start and end distances.
