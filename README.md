# C++ Project Template
C++ project template that uses CMake and GoogleTest, and has dynamic features such as:
  * Automatic project naming (the same as the parent directory, e.g. `cpp-project-template` and `cpp-project-template_Test`
  * Automatic GoogleTest import
  
Prequisities:
  * CMake
  * Ninja
  * Clang / LLVM (or GNU GCC / G++)
  
To build project:
 1. `cmake -G Ninja -B build/`
 2. `cmake --build build`
 
To run the project after building:
 * `./build/{project_name}` or `.\build\{project_name}.exe`
