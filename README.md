# Python3 GDS to OBJ (Wavefront) files converter script

This first version was built to create `.obj` 3D files from SDK130 PDK `.gds` files

Lot of the work is based on the gdsiistl repo: https://github.com/dteal/gdsiistl

Python libraries requirements:
```
numpy
gdspy
triangle
```

## Usage:
`python3 gds2obj.py file.gds`

Outputs one file per layer named  `file.gds_layername.gltf` in the same folder as the original gds file


## Note from original gdsiistl script:

Due to a limitation of the library used to triangulate the polygonal boundaries of the GDSII geometry, the polygon borders (i.e., all geometry) are shifted slightly (by a hardcoded delta of about 0.00001 units, or 0.01 nanometers in standard micron units) before export. Furthermore, due to another related limitation/bug (not yet completely understood; see source code comments), extra triangles are sometimes created covering holes in polygons.

So the output mesh is not guaranteed to be watertight, perfectly dimensioned, or retain all polygon holes, but it should be arbitrarily close and err on the side of extra triangles, so a program (e.g., Blender) can edit the mesh by deleting faces and produce a negligibly-far-from perfect visualization.








 