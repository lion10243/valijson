cmake_minimum_required(VERSION 3.2 FATAL_ERROR)

project (valijson VERSION 0.1 LANGUAGES CXX)

add_library(valijson INTERFACE)

target_include_directories(valijson INTERFACE  
    $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>  
    $<INSTALL_INTERFACE:include> 
)

install(TARGETS valijson EXPORT valijsonConfig)
install(DIRECTORY include/ DESTINATION include)
install(EXPORT valijsonConfig DESTINATION cmake)
export(TARGETS valijson FILE valijsonConfig.cmake)
