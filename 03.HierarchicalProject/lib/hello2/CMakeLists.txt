# 현재 CMake 스크립트를 사용하는데 최소한의 버전을 명시한다.
cmake_minimum_required(VERSION 3.0)

# 프로젝트 명과 C++을 사용한다고 명시한다. 
project(hello2 CXX)

# 해당 프로젝트에서 사용될 C++ 버전을 17로 지정한다.
set(CMAKE_CXX_STANDARD 17)

# add_library(<name> STATIC|SHARED source) sources 파일들에 대한 라이브러리를 생성한다.
# so 라이브러리를 생성할 경우 (기본 STATIC 이다.)
# add_library(applib SHARED foo.cpp)
add_library(${PROJECT_NAME} foo.cpp)

# target_include_directories()는 PROJECT_NAME 프로젝트에 include 경로를 추가한다.
# CMAKE_SOURCE_DIR은 최정상위 CMakeLists.txt 파일이 있는 폴더의 경로를 가리킨다.
target_include_directories(${PROJECT_NAME}
PUBLIC
    ${CMAKE_SOURCE_DIR}/include/hello2
)