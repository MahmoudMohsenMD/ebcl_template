cmake_minimum_required(VERSION 3.12)

project(MyJsonApp)

set(CMAKE_CXX_STANDARD 11)

# Include GNUInstallDirs to determine the correct values for CMAKE_INSTALL_*
include(GNUInstallDirs)

# Find the JSONCPP library
find_package(PkgConfig REQUIRED)
pkg_check_modules(JSONCPP REQUIRED jsoncpp)

# Add the include directories for JSONCPP
include_directories(${JSONCPP_INCLUDE_DIRS}) 

# Add the executable
add_executable(MyJsonApp main.cpp)

# Link against the JSONCPP library
target_link_libraries(MyJsonApp ${JSONCPP_LIBRARIES})

# Installation configuration
install(TARGETS MyJsonApp DESTINATION ${CMAKE_INSTALL_BINDIR})
#SET (CPACK_SET_DESTDIR "/usr/bin/")
