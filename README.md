# Demo_vtk

## BUILD
1. Change the value of *VTK_ROOT* and *Qt5_ROOT* in *CMakeLists.txt*
If you use linux, you can add your VTK to environment variable and comment out *VTK_ROOT* and *Qt5_ROOT*

2. Change the value of *CMAKE_BUILD_TYPE* in keep with your version of VTK

3. `cd Demo_vtk`

4. `cmake .`

5. `make`

6. `./Demo_vtk`