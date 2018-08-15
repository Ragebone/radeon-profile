cmake_minimum_required(VERSION 3.10)

project(radeon-profile)

set(CMAKE_INCLUDE_CURRENT_DIR ON)
set(CMAKE_AUTOMOC ON)
find_package(Qt5Widgets REQUIRED)

# ┌──────────────────────────────────────────────────────────────────┐
# │  Source file                                                     │
# └──────────────────────────────────────────────────────────────────┘

file(GLOB_RECURSE source radeon-profile/*.cpp)
include_directories(src)

# ┌──────────────────────────────────────────────────────────────────┐
# │  Applications  (entry points)                                    │
# └──────────────────────────────────────────────────────────────────┘

# FractalCreation
add_executable(radeon-profile radeon-profile/main.cpp ${source})
qt5_use_modules(radeon-profile Widgets Core Gui Network Charts)