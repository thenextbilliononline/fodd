---
title: 3D Modeling
permalink: /3D_Modeling/
---

This page is about creating models for 3D-printing. It's mostly geared towards Sudoers using our [Type-A Machine](/Type_A_Machine "wikilink") 3D printer, but models can be made by anyone anywhere, just like word documents don't have to be made on a machine attached to a 2D printer.

STL Models
----------

STL files are wireframe/polygonal representations of a 3D model. There's a number of ways to get them:

### Write OpenSCAD (recommended)

[OpenSCAD](http://www.openscad.org/) is a programming language for describing 3D shapes. You write code on the left, and it renders your model on the right. Then you can export an STL file. It has many benefits:

-   free, open source, cross-platform
-   keyboard-centric, less mouse dragging
-   your models are deterministic
-   you can easily track your changes with git
-   the [manual](https://en.wikibooks.org/wiki/OpenSCAD_User_Manual) is pretty straightforward
-   there's even a [browser javascript version](http://openjscad.org/)!

But the software still has a long way to go. Some annoying things about OpenSCAD:

-   single-threaded rendering, so complex models take a long time
-   no persistent cache, so if you close it, you must render all over again
-   GUI blocks on rendering, so if your render takes too long you must kill it (save often)
-   volatile syntax - for example, child() is deprecated in git master, but the alternative children() is not even supported by latest stable (2013.06)

### Use other modeling software

-   Google Sketchup is exceptionally easy to use because they profit when you map buildings for them.
-   [Tinkercad](http://tinkercad.com) (in Google Chrome)
-   [Blender](http://blender.org)

### Download them

You can find premade STL files:

-   On [Thingiverse](http://thingiverse.com/)
-   On the [local file server](smb://space/sudoroom%20public%20data/Projects/3DPrinting)
-   On sudoroom's [github](https://github.com/sudoroom) ([magnets](https://github.com/sudoroom/magnets), [blocks](https://github.com/sudoroom/sudo-blocks), etc)

Slicing
-------

3D Printers don't understand OpenSCAD or STL. They understand an extension of gcode, which is a decades-old language which sends direct instructions such as “heat to 100 degrees, move here, do this, move there, do that, cool down”. In order to print a model you have to turn it into a series of 2D layers or “slices”, using a program called a “slicer”. Slicers output gcode. They need to be configured for a particular printer, with settings such as melting tempurature, bed size, fill style, overhang compensation, etc. Examples of slicing software:

-   Slic3r
-   KISSlicer
-   Skeinforge

Slicing for a particular machine such as our [Type-A](/Type_A_Machine "wikilink") should be documented at its own page.

[Category:3DPrinting](/Category:3DPrinting "wikilink")