# Manual / Spec Overview


## Overview

### Create a multi-platform / engine compatible avatar collection, with the following spec: 


---

- easily remixable
- rigged and weighted (all assets / traits)
- expressable and pilotable
- VRM format compatibility
- Portability multiple engines / formats (VRChat, Unity, etc)
- good optimization
- clean archive of collection master
- looks like a [fumofumo](https://fumo.website/img/001.jpg) plush! 

---

## Original File Review

### The original files mostly *look* good (visually), but there are some overarching issues (mainly on a technical / compatibility level). 

---

### Base model does not look like a fumo

The existing base models are vaguely fumo-like but [do not actually look like a fumo plush](https://hackmd.io/_uploads/ryUsm8GWel.png).
Fumo plushes generally have a [consistent base look and fabric pattern](https://media.discordapp.net/attachments/808471987689226280/1372258459227127808/Overview3x.png?ex=68261ec8&is=6824cd48&hm=db38fba223fa15778ebc633479147e92448c9584e46b972f4aa765b1429a2e76&=&format=webp&quality=lossless&width=2928&height=2070), and have additional features stitched onto this base. 

### Unrigged / no weights

We can simply rig everything up and make things work in a humanoid rigging standard, compatible with VRM & Unity. 
This would open up usecases for animations, VR usage, digital pets; etc. 

### No expressions / visemes / emotes, etc

We can create an expression set of shapekeys to allow the avatar to 

### Shader spec non-consistent / not glTF compatible

There's a lot of different shader nodes / setups going on that will not export as glTF, or rely on internal Blender nodes. We can unify these into a glTF standard, making it portable, and make it easily remixable, as well as adaptable for other texture specs. 


### UVs for current models are not optimal or human readable

Currently the UVs for a lot of assets are sub-optimal in terms of texture coverage, stretching and "human-readability" (how easy it is to look at a UV and discern how it's working, how easy it would be to remix)

In editing or remake phase for assets, we can do the following: 

- Generally improve UV layouts' texture usage
- Unify texel density, so things like tilables (cloth normal maps, etc) are uniform in nature
- Make them "human-readable", making them easy for editing and remixing

*We can possibly do the following, though it would increase lead times:*

- make them functional as a fabric pattern (for physicals)


### Textures / shading could be improved

Currently the textures / shaders could stand to be improved in a few ways: 

- the body materials do not look like fabric / "fumo-ish"
- unecessary usage of multiple material slots
- some odd/unnecessary usage of textures (displacement, etc)



---


## Specification & Guidelines

**We can create an asset specification & guideline in order to conform with the [Overview](https://hackmd.io/zUCXAgzfTNOztkI-sEfJrQ?stext=24%3A11%3A1%3A1747244636%3AtV_0Vl&both=) stated at the start of this document.**

### "Easily remixable"

- Assets should have singular material slots (where possible)
- Assets should have human-readable, correctly oriented UVs. If possible, they should be mirrored on the U axis in UV space, and be centered to the center of UV space. 
- Assets in the collection should be easy to understand consistently named. 
    - Mesh name should match datablock name
    - Material name should match Mesh name
- Assets should be "self-contained", eg. not specifically relying on a material set from another asset, etc.
    - No texture references to other assets in materials, etc.  
- Consistent armature spec with readable bone naming scheme
    - No difference in armatures across variations
    - Human readable bone naming
- Transforms should be normalised and applied where relevant

### "Rigged and weighted"

- Base model should be weighted and conforming to a humanoid spec
- Armature spec should be VRM compatible & Unity Mecanim compatible
- Clothing, accessories and traits should be all correctly weighted and parented

### "Expressable and pilotable"

- Fullbody tracking capable armature
- Expressions for VRM spec
    - Eyelook
    - Blink
    - Speech
    - Emotion
- Use eye trait as default expression
    - Use unified spritesheet for everything non-default (one set of expressions, default is the trait exception)

### "VRM format compatibility"

- Use glTF specification shaders / materials
    - Determine if using PBR / MToon / Both
- Compatible armature spec
- Compatible shapekey spec
- Embedded metadata
    - Usage
    - Licencing (this includes custom licencing. eg VPL)
    - Misc (versioning, creators, etc) 

### "Portability"

- Determine where these will most likely be used and adjust accordingly
- Keep collection master in an open-source software eg. Blender
- Make final outputs as portable as possible. (VRM, texture spec, etc.) 
- Other considerations already mentioned, eg. shader spec, armature spec, etc. 

### "Good optimization"

- Limit total polygonal budgets
    - Consider worst possible trait case - what's the highest total polycount using the highest polycount assets? 
- Use good UV prinicples to maximise texture usage, ergo increasing quality in more optimized texture sizes
- Limit maximum texture resolution
- Mesh area (*not* polygonal density) based texture size priority
    - Bear in mind texel density though
- Limit material counts to one per trait
- Consider intended usage in VRChat. [There are performance ranks and specification for PC & Quest.](https://creators.vrchat.com/avatars/avatar-performance-ranking-system/) 

### "Clean archive of collection master"

- Deliver a packed archive of the traits in form of a Blender collection file
    - Strip any third-party code or assets that shouldn't be distributed with it (custom scripts, etc)
    - Ensure no miscellaneous / unused meshes or data is still present (orphan purge, etc)
- Keep clean, no material assigned versions of base assets (textureless)
    - think VRoid - clean base assets to remix

### "Looks like a fumofumo!"

NOTE: This is a much wider consideration that compasses geometry, UVs, materials, etc. 

Generally speaking, it would be smart to approach the collection as if it was a *real* fumo collection - use real world principles for material decisions, texturing, and UVs

- Remake body model

- Geometry and UVs should align with the concept of papercraft / fabric patterns
    - This means we can use PBR stitching tools and UV shell boundary stitching, etc.
    - Buttons etc should seem "stitched on", etc
    - Will look and feel more in alignment with a fumo

- Use embroidery material for eye / expression traits
    - Fumo eyes / brows / mouths are made of stitching. Use a stitching material to emulate this.
    - Use binary expressions


- Realistic fabric based normals as basis for components that would be cloth based in the real world
    - eg. "Skin" should be felt / fabric
    - Accessories should be seperate based on real world application. 


## Task list

### Remake base model

Use the Fumo stitching pattern to create a more accurately constructed base model. 

---

### Determine which traits can reuse meshes / are texture variants

Certain traits like hats are simply retextures. Determine which these are - this helps reduce modelling time. 

### Determine which, if any, traits can be reused from the original set

Some assets are probably fine as-is, or with minor tweaks. Determine these and check a checklist. 

---


### Determine which assets need modelling

Checklist / progress chart of assets to be remade

---

### Create / determine expression set

[See above](https://hackmd.io/zUCXAgzfTNOztkI-sEfJrQ?both=&stext=4091%3A31%3A1%3A1747247565%3ABrV3oQ) - create a unified expression set, that uses the eyes trait as it's default / basis expression, using a sprite sheet.

---
