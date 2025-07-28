<!--
Keep this document short & concise,
linking to external resources instead of including content in-line.
See 'release/text/readme.html' for the end user read-me.
-->

Goo Engine 3.6.23
==========

Even though Blender 3.6 LTS has reached its end-of-life, many people still depend on 3.6.

I need 3.6 specifically for MMD Tools & UuuNyaa Tools, and plan to use 3.6 long after the EOL, so I patched Goo Engine 3.6 with fixes from Official 3.6 LTS branch.

## Building for macOS
I don't use Blender on Windows / Linux, so I cannot test it. But you can still build it yourself. [You can learn how to build Blender here.](https://developer.blender.org/docs/handbook/building_blender/)

**Attention!! You have to use OpenGL backend to use Goo Engine on macOS**

You need Xcode 15.4 to build Blender 3.6. Xcode 15.4 won't launch in Sequoia, but that's fine.
Xcode 16.3+ won't do it because it comes with Clang 17.

1. Remove current Command Line Tools:
```bash
sudo rm -rf /Library/Developer/CommandLineTools
```

2. Install Command Line Tools 16.2, and Xcode 15.4. CLT is for good measure.
Get them from https://developer.apple.com/download/all/ (you need Apple Account)

3. run this command.
```bash
sudo xcode-select -s /Library/Developer/CommandLineTools
```

4. after that:
```bash
mkdir ~/blender-git
cd ~/blender-git
git clone -b merge-blender-v3.6 https://github.com/ulyssas/goo-engine.git
cd goo-engine
make update
make
```

Then, you should get `Blender.app` in `~/blender-git/build_darwin/bin`.


Goo Engine
==========

Goo Engine is a version of Blender by [DillonGoo Studios](https://www.youtube.com/dillongoo) with some key modifications
to the source code that allow us to focus on NPR and Anime style rendering. Key features include the four custom Shader 
nodes we added to Eevee and Light Groups. You can learn about them on the 
[Professor Goo YouTube channel](https://www.youtube.com/@professorGoo>).

Some have asked why we haven't pushed these changes to Blender's master branch: 
this is because many of these features would not be accepted as they are and may destablize other features like Cycles.
We only use Eevee for NPR so we prioritize specific features which the Blender Institute understandably can't afford to 
make compromises for. This allows us to develop and test quickly. However, we do actively update Goo Engine to keep up 
with the native Blender branch so they can evolve side by side. We also regularly add and improve custom features as we 
use Goo Engine on projects at the studio. [Stay tuned](https://twitter.com/dillongoostudio>) for updates.

Get the pre-built download on the [Patreon page](https://www.patreon.com/dillongoo) to support continued development of 
Goo Engine.


Blender
=======

Blender is the free and open source 3D creation suite.
It supports the entirety of the 3D pipeline-modeling, rigging, animation, simulation, rendering, compositing,
motion tracking and video editing.

![Blender screenshot](https://code.blender.org/wp-content/uploads/2018/12/springrg.jpg "Blender screenshot")

Project Pages
-------------

- [Main Website](http://www.blender.org)
- [Reference Manual](https://docs.blender.org/manual/en/latest/index.html)
- [User Community](https://www.blender.org/community/)

Development
-----------

- [Build Instructions](https://wiki.blender.org/wiki/Building_Blender)
- [Code Review & Bug Tracker](https://projects.blender.org)
- [Developer Forum](https://devtalk.blender.org)
- [Developer Documentation](https://wiki.blender.org)


License
-------

Blender as a whole is licensed under the GNU General Public License, Version 3.
Individual files may have a different, but compatible license.

See [blender.org/about/license](https://www.blender.org/about/license) for details.
