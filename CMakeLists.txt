cmake_minimum_required(VERSION 3.15)
project(multiplot VERSION 1.0 LANGUAGES Fortran)

#Set compiler flags for GNU Fortran
if(CMAKE_Fortran_COMPILER_ID STREQUAL "GNU")
    set(CMAKE_Fortran_FLAGS "${CMAKE_Fortran_FLAGS} -ffree-line-length-none -Wno-error=line-truncation")
endif()

if(CMAKE_Fortran_COMPILER_ID STREQUAL "Intel")
    set(CMAKE_Fortran_FLAGS "${CMAKE_Fortran_FLAGS} -extend-source")
endif()

add_subdirectory(src)

add_subdirectory(TESTING)

