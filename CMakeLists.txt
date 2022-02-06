cmake_minimum_required(VERSION 3.14)

project(h5wasm
    VERSION 1.0.0
    DESCRIPTION "HDF5 C/C++ libaries for WebAssembly"
    LANGUAGES C CXX)

add_library(h5wasm INTERFACE)
target_include_directories(h5wasm INTERFACE include)
target_link_options(h5wasm INTERFACE ${CMAKE_SOURCE_DIR}/lib/libhdf5.a ${CMAKE_SOURCE_DIR}/lib/libhdf5_hl.a)

add_library(h5wasm_cpp INTERFACE)
target_include_directories(h5wasm_cpp INTERFACE include)
target_link_libraries(h5wasm_cpp INTERFACE h5wasm)
target_link_options(h5wasm_cpp INTERFACE ${CMAKE_SOURCE_DIR}/lib/libhdf5_cpp.a ${CMAKE_SOURCE_DIR}/lib/libhdf5_hl_cpp.a)
