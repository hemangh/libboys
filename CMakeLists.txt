cmake_minimum_required(VERSION 3.15)
project(multiplot VERSION 1.0 LANGUAGES Fortran)

#Set compiler flags for GNU Fortran
if(CMAKE_Fortran_COMPILER_ID STREQUAL "GNU")
    set(CMAKE_Fortran_FLAGS "${CMAKE_Fortran_FLAGS} -m64 -cpp -ffixed-line-length-none -ffree-line-length-none -fdefault-integer-8 -finit-local-zero -Ofast -mtune=native -march=native -ffast-math -march=native -mfpmath=sse -msse2 -ffast-math -g -fPIC")
endif()

if(CMAKE_Fortran_COMPILER_ID STREQUAL "Intel")
    set(CMAKE_Fortran_FLAGS "${CMAKE_Fortran_FLAGS} -extend-source")
endif()

add_subdirectory(src)

add_subdirectory(TESTING)