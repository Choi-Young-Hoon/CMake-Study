# 현재 CMake 스크립트를 사용하는데 최소한의 버전을 명시한다.
cmake_minimum_required(VERSION 2.4)

# 프로젝트 명과 C++을 사용한다고 명시한다. 
project(boost_example CXX)

# 해당 프로젝트에서 사용될 C++ 버전을 17로 지정한다.
set(CMAKE_CXX_STANDARD 17)

set (FFMPEG_LIBRARY_DIR ${FFMPEG_DIR}/lib)

# 아래와 같이 직접 라이브러리 파일을 찾을 수도 있음.
# set (FFMPEG_LIBRARY_DIR ${FFMPEG_DIR}/lib)
# find_library(FFMPEG_AVCODEC_LIB NAMES libavcodec.a HINTS ${FFMPEG_LIBRARY_DIR} REQUIRED)
find_package(Boost COMPONENTS chrono) # boost의 chrono 라이브러리를 찾는다.
if (Boost_FOUND)
    message("Find boost library @@@@@@@@@@@@@@@@@2")

    include_directories(${Boost_INCLUDE_DIRS})
    add_executable(app main.cpp)
    target_link_libraries(app ${Boost_LIBRARIES})
else()
    message("LOL..... @@@@@@@@@@@@@@@@@@@@@@@@@@@@@")
endif()