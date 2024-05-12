# TODO 1: Set the minimum required version of CMake to be 3.10
cmake_minimum_required(VERSION 3.10)

# TODO 2: Create a project named Tutorial
project(Tutorial VERSION 1.0)

# TODO 7: Set the project version number as 1.0 in the above project command
# project(Tutorial
#     VERSION 0.1.0
#     DESCRIPTION "a simple CMake example project"
#     # HOMEPAGE_URL ""
#     LANGUAGES CXX
# )

# TODO 6: Set the variable CMAKE_CXX_STANDARD to 11
#         and the variable CMAKE_CXX_STANDARD_REQUIRED to True
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)

# if(TTUTORIAL_BUILD_TESTING)
#   enable_testing()
#   # or alternatively, `include(CTest)`, if you want to use CDash
#   # https://cmake.org/cmake/help/book/mastering-cmake/chapter/CDash.html
# endif()

# set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_SOURCE_DIR}/build)
# set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${PROJECT_SOURCE_DIR}/lib)
# set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${PROJECT_SOURCE_DIR}/lib)

# add_subdirectory(libs/module1)
# add_subdirectory(libs/module2)
# if module1 is a library, use add_library() instead
# add_executable(module1
#   src/module1.cpp
# )

# TODO 8: Use configure_file to configure and copy TutorialConfig.h.in to TutorialConfig.h
# configure_file(TutorialConfig.h.in TutorialConfig.h)

configure_file (TutorialConfig.h.in "${PROJECT_BINARY_DIR}/TutorialConfig.h")

# TODO 3: Add an executable called Tutorial to the project
# Hint: Be sure to specify the source file as tutorial.cxx
add_executable(Tutorial tutorial.cxx)

# TODO 9: Use target_include_directories to include ${PROJECT_BINARY_DIR}
# this will add the binary tree to the search path for include files so that we will find TutorialConfig.h
target_include_directories(Tutorial PUBLIC "${PROJECT_BINARY_DIR}")

# this line also works:
# include_directories("${PROJECT_BINARY_DIR}")
