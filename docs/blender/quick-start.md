# Quick start

Five minutes, from loading a preset to your first SolidRocks render.

## 1. Load a preset

At the top of the panel, choose the preset that matches your scene: **Studio**, **Interior** or **Exterior**.

!!! note "Author"
    Use the exact preset names of the final build here (e.g. SR_Studio).

## 2. Switch SolidRocks on

Click **SolidRocks: OFF**. It turns to **SolidRocks: ON**.

Your current Cycles settings are saved, then replaced by the values of the chosen level. Click again at any time to get your own settings back.

## 3. Choose a level

Move the **Level** slider:

| Level | Use it for |
|---|---|
| Draft, Low | Blocking, lighting tests |
| Medium, Good | Look development, client previews |
| Very Good, Prod | Final images |
| Ultra | Very demanding scenes, print |

Start at **Good**. Render with **F12** as usual.

## 4. Not sure which level? Let SolidRocks measure it

In the **Tune** tab, click **Guess Optimal Level**. SolidRocks renders small test areas at each level and tells you the fastest level that stays below the noise target. It only recommends: you move the slider yourself.

## 5. Using the denoiser?

Switch **Denoise** on next to the SolidRocks button. The preset then lowers the samples and loosens the noise threshold, because the denoiser cleans up the rest. On our test scenes, this made renders 20 to 40 % faster than with no reduction, with no visible difference at 100 % zoom.

!!! tip
    Judge noise with **Denoise off**, then switch it on for the final render.
