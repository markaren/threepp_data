# fjord

Assets for threepp's `examples/vulkan/vulkan_fjord`.

## trees/

Card trees: Poly Haven's scanned tree models rebuilt as leaf-card LODs (`card` near, `lite` far,
three variants each) by the Nørvasundet twin's Blender pipeline, then quantised for size:

- `<species>.tree`: every mesh of a species, format `TRE1` (16-bit positions and UVs, 8-bit normals and
  baked canopy occlusion). Reader: `examples/vulkan/fjord_trees.hpp`.
- `<species>_card.webp`, `<species>_lite.webp`: leaf atlases (sRGB, lossless alpha, cutout at 0.4).
- `<species>_bark.webp`, `<species>_bark_n.webp`: bark colour (sRGB) and normal (OpenGL +Y).
- `impostor_albedo.webp`, `impostor_normal.webp`: the far tier's impostor atlas, every `lite` variant
  seen from the front and the side (128x256 cells; row = species, column = variant * 2 + view), baked
  from the files above by `scripts/fjord/bake_tree_impostors.py` in threepp.

UVs are glTF-style (v runs down the image): load the images without the vertical flip.

Sources, all Poly Haven (https://polyhaven.com), CC0 1.0 (public domain):

- Fir Tree 01, https://polyhaven.com/a/fir_tree_01 (`spruce`)
- Pine Tree 01, https://polyhaven.com/a/pine_tree_01 (`pine`)
- Tree Small 02, https://polyhaven.com/a/tree_small_02 (`birch`, a stand-in broadleaf)

## terrain/

Terrain structure bands in the layout of `terrain::makeBandMaps` (albedo: 0.5-neutral linear overlay with
height in A; nr: tangent normal in RG, roughness modulation in A), packed from Poly Haven drone scans:

- Rocky Terrain 02 by Amal Kumar, https://polyhaven.com/a/rocky_terrain_02, CC0 (`grass`)
- Aerial Rocks 02 by Rob Tuytel, https://polyhaven.com/a/aerial_rocks_02, CC0 (`rock`)
- Aerial Rocks 01 by Rob Tuytel, https://polyhaven.com/a/aerial_rocks_01, CC0 (`scree`)
