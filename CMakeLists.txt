cmake_minimum_required(VERSION 3.10)
project(indi-astrolink4max VERSION 1.0 LANGUAGES C CXX)

# allow custom cmake modules in the repository
set(CMAKE_MODULE_PATH "${CMAKE_CURRENT_SOURCE_DIR}/cmake_modules/${CMAKE_MODULE_PATH}")

# prefer modern CMake handling of install locations
include(GNUInstallDirs)

# Use a modern way to request C++11
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

# Find INDI (keeps the original behavior)
find_package(INDI REQUIRED)

# include any common macros/helpers provided in the repo
include(CMakeCommon OPTIONAL)

################ AstroLink4 MAX ################

set(indi_astrolink4max_SRCS
    ${CMAKE_CURRENT_SOURCE_DIR}/indi_astrolink4max.cpp
)

add_executable(indi_astrolink4max ${indi_astrolink4max_SRCS})

# modern include directives for the target
target_include_directories(indi_astrolink4max
    PRIVATE
        ${CMAKE_CURRENT_BINARY_DIR}
        ${CMAKE_CURRENT_SOURCE_DIR}
        ${INDI_INCLUDE_DIR}
)

# link against the INDI driver library
target_link_libraries(indi_astrolink4max PRIVATE indidriver)

# installation rules using GNUInstallDirs
install(TARGETS indi_astrolink4max
    RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR}
)

# install the driver XML into the INDI data directory (provided by FindINDI)
if(DEFINED INDI_DATA_DIR)
    install(FILES indi_astrolink4max.xml DESTINATION ${INDI_DATA_DIR})
else()
    message(WARNING "INDI_DATA_DIR is not defined; indi_astrolink4max.xml will not be installed.")
endif()