cmake_minimum_required(VERSION 3.15)
project(hjonk C)

set(CMAKE_C_STANDARD 11)

# vcpkg static linking
set(VCPKG_TARGET_TRIPLET "x64-windows-static" CACHE STRING "")
set(CMAKE_MSVC_RUNTIME_LIBRARY "MultiThreaded")

find_package(CURL CONFIG REQUIRED)
find_package(cJSON CONFIG REQUIRED)

add_executable(hjonkapi hjonk.c)

target_link_libraries(hjonk
    PRIVATE
    CURL::libcurl
    cjson
)

# Windows system libs curl depends on
if(WIN32)
    target_link_libraries(hjonkcli PRIVATE
        ws2_32
        wldap32
        crypt32
        bcrypt
        normaliz
    )
endif()
