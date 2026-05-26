# threepp-data

Runtime assets (models, textures, fonts, sounds, images, URDF) for the
[threepp](https://github.com/markaren/threepp) examples and tests.

These are fetched on demand via CMake `FetchContent` when threepp is built with
`THREEPP_BUILD_EXAMPLES` or `THREEPP_BUILD_TESTS` enabled. Consumers who use
threepp purely as a library do **not** need this repository.
