set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -w -fpermissive -Wno-error -Wno-return-type")
set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -w -fpermissive -Wno-error")

cmake_minimum_required(VERSION 3.12)

include_directories(
        ${CMAKE_CURRENT_LIST_DIR}/opus/include
)

find_package(shadowhook REQUIRED CONFIG)
add_subdirectory(opus)
add_subdirectory(multiplayer)

target_compile_options(opus PRIVATE -O3)
