# Introduction

Scripting language, certain syntax 
Extensible, opensource -> manages the build process in compiler independent manner. 

We want to run C++ application on windows, Linux, ios etc. Target is to build the final binary.
It is not the build system, rather build system generator. 
Structure the complete project in the CmakeLists.txt(script file):
    1. Info on the compilers, headers., .cpp
    2. Specify how it will be running on th platform.

Pass the file to Cmake engine -> It will process it -> see the operating system and work with it accordingly.
compile source code, create libraries, generate wrappers and build executable binaries.
We get set of platform dependent file:
    1. Windows: Visual Studio project files.
    2. Linux: Make project files.

CMake scripts also make source management easier because it simplifies build script into one file and more organized, readable format.

Such files will easily build on the platform, to get the binary to run.

Build logic and definitions with CMake language is written either in CMakeLists.txt or a file ends with <project_name>.cmake. But as a best practice, main script is named as CMakeLists.txt instead of cmake.

CMakeLists.txt is placed at the root of the source tree of any application, library it will work for.
If there are multiple modules, and each module can be compiled and built separately, CMakeLists.txt can be inserted into the sub folder.

.cmake files can be used as scripts, which runs cmake command to prepare environment pre-processing or split tasks which can be written outside of CMakeLists.txt. These projects can be separated build processes for libraries or extra methods for complex, multi-module projects.

Writing Makefiles might be harder than writing CMake scripts. CMake scripts by syntax and logic have similarity to high level languages so it makes easier for developers to create their cmake scripts with less effort and without getting lost in Makefiles.

Some commonly used commands

message: prints given message
cmake_minimum_required: sets minimum version of cmake to be used
add_executable: adds executable target with given name
add_library: adds a library target to be build from listed source files
add_subdirectory: adds a subdirectory to build
