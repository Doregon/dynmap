# Dynmap™ - dynamic web maps for Minecraft servers

## This branch is not production ready.

This branch is composed of @Doregon's work on asynchronous chunk loading and unloading for Dynmap, supported on servers running PaperSpigot, or PaperMC, using the PaperLib repositories to make certain functions async-compatible. This will make Dynmap perform better, as it can run multiple renders at once, and help prevent _as much_ server lag from being produced when rendering.

If PaperMC is not in use, such as when using Spigot, Bukkit, or CraftBukkit, the asynchronous functionality will be disabled in favor of the same old operations of Dynmap.

The PaperMC/PaperLib repository states that it should work with 1.12+, but we're not using any classes that have support for >1.13.1. The final result of this code will be limited by that--however versions prior to 1.13.1 will still be able to use synchronous loading. Here is the expected result:

* PaperMC versions >= 1.13.1 will be able to leverage multiple threads to render.
* PaperMC versions <= 1.13 will fall back to synchronous functionality to render.
* Non-PaperMC, Bukkit-based software won't be affected.
* Non-Bukkit based software won't be affected.
* **All without requiring addons or breaking compatibility.**

If integrating directly into Dynmap fails, I'll develop an addon for the time being.

**Ye shall be warned:** This branch will be a playground, with commits coming in particularly fast. The main files that will be changed for testing are the files in the `bukkit-helper-116-4` directory and the `build.gradle` file on the root. All other files will be equivalent until testing and compilation is completed, in which case all of the changes will slowly be rolled out to each `bukkit-helper-*` directory. Do not expect to see successful builds on directories that are being rapidly updated, as most of the time they will fail. However, if you wish to build and report on solutions, open an issue and post a solution.

Dynmap is a trademark of Michael Primm, TX USA.  All Rights Reserved.
