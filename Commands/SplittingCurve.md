# SplittingCurve

![Status = In Test](https://img.shields.io/badge/Status-Testing-yellow?style=for-the-badge&logoColor=white&logo=Statuspal)
![Bugs = Found](https://img.shields.io/badge/Bugs-Found-critical?style=for-the-badge&logoColor=white&logo=OpenBugBounty)
![Version = 0.1.0](https://img.shields.io/badge/Version-0.1.0-informational?style=for-the-badge&logoColor=white&logo=Verizon)
![Author = cgburgos](https://img.shields.io/badge/Author-cgburgos-informational?style=for-the-badge&logoColor=white&logo=Anchor)

## Description

> The SplittingCurve commands allow you split all the Brep geometries based on the world planar projection of the selected curve. The output is two groups of geometries (Inside and outside the curve region). **This is specially useful for creating splitted sections and isometrics**. The original geometry gets hidden.

<!--  -->

> _It's under consideration to make the output generate new layers._

## Inputs

1. **Geometries to split** _(External)_: Polysurface or multiple-face, Mesh and extrusions. They might be open or closed.
2. **An open Curve** _(External)_: It must be big enough to be able to create a surface under the elements to split.
3. **Offset Direction and Distance Point** _(Internal)_: A point where the curve is going to be offseted to.
4. **Geometries to split** _(External)_: Polysurface or multiple-face, Mesh and extrusions. They might be open or closed.
5. **An open Curve** _(External)_: It must be big enough to be able to create a surface under the elements to split.
6. **Offset Direction and Distance Point** _(Internal)_: A point where the curve is going to be offseted to.

## Options

- **Elements Warning** `(GoTrough/Cancel)`: Proceed without saving before a heavy resource intense operation. `GoTrough` will keep the execution of the command. `Cancel` will abort the operation.
- **Surface cover points** `(Yes/No)`: After the inside surface is created, check if it covers all the elements you want to split. It will run until a surface it's accepted or the whole operation is cancelled by the user. `Yes` will accept the given surface and will proceed with the operation. `No` will allow the user to select the offset point again.

## Step by step

1. Draw a curve (It can be a Curve, Polyline or Line) that exceeds all the geometries that you want to split. It has to be planar, meaning it should not have a variation on the z axis.
2. Run the command `SplittingCurve`.
3. Select the objects you want to split. They can be the geometries described on the inputs point.
4. Select the curve drew on the first step.
5. Pick a point to create an offset of the curve that allows to create a ruled surface that contains where all the geometries on one group of the split.
6. Accept/Redo the result surface.
7. The result will be the input geometry splitted in two groups. The ones that were inside the surface created on the process and the one outside. The splitted geometries will be placed on the active layer. The original geometries are hidden. To display them again, run the `show` command

## Video

<a href="https://www.youtube.com/watch?feature=player_embedded&v=B3U8UYqORvY
" target="_blank"><img src="../res/timg/SplittingCurve.png"
alt="IMAGE ALT TEXT HERE"  height="500" /></a>

## Observations

- If more than 100 elements are selected, the command will run a warning before continuing in order to be able to save, because Rhino might get unstable.
- Some unreliability issues for complex models have been detected and will be patched on next version.
<!-- CHECK IF ITS POSSIBLE TO INTEGRATE GITHUB BUGS INTO THIS FORM -->

## Rhino Compatibility

![Rhino = 5](https://img.shields.io/badge/-5-inactive?style=for-the-badge&logoColor=white&logo=Rhinoceros)
![Rhino = 6](https://img.shields.io/badge/-6-green?style=for-the-badge&logoColor=white&logo=Rhinoceros)
![Rhino = 7](https://img.shields.io/badge/-7-green?style=for-the-badge&logoColor=white&logo=Rhinoceros)
![Rhino = 8](https://img.shields.io/badge/-8-yellow?style=for-the-badge&logoColor=white&logo=Rhinoceros)

---
