cmake_minimum_required (VERSION 2.6)

#those two lines may be required, depending on your system, using the apropriate paths for your system.
include_directories(/usr/local/include)
link_directories(/usr/local/lib)

project(OmegaMaxEnt)

add_executable(OmegaMaxEnt graph_2D.cpp graph_3D.cpp generique.cpp OmegaMaxEnt_data.cpp OmegaMaxEnt_main.cpp)

target_compile_options(OmegaMaxEnt PRIVATE -std=c++11 -O0)

target_compile_definitions(OmegaMaxEnt PRIVATE ARMA_DONT_USE_WRAPPER)

target_link_libraries(OmegaMaxEnt blas lapack fftw3)

install(TARGETS OmegaMaxEnt DESTINATION bin)

