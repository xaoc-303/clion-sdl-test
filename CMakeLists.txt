cmake_minimum_required(VERSION 3.2)
project(test1)

set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "${test1_SOURCE_DIR}/cmake")
find_package(SDL2 REQUIRED)
find_package(SDL2_Image REQUIRED)
#find_package(SDL2_ttf REQUIRED)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

set(SOURCE_FILES main.cpp)
add_executable(test1 ${SOURCE_FILES})

include_directories(${SDL2_INCLUDE_DIR}
                    ${SDL2_IMAGE_INCLUDE_DIR}
                #    ${SDL2_TTF_INCLUDE_DIR}
                  )
target_link_libraries(test1 ${SDL2_LIBRARY}
                             ${SDL2_IMAGE_LIBRARIES}
                      #       ${SDL2_TTF_LIBRARIES}
                           )