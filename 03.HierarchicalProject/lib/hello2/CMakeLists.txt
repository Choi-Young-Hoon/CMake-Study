# 현재 CMake 스크립트를 사용하는데 최소한의 버전을 명시한다.
cmake_minimum_required(VERSION 3.0)

# 프로젝트 명과 C++을 사용한다고 명시한다. 
project(hello2)

# add_library(<name> STATIC|SHARED source) sources 파일들에 대한 라이브러리를 생성한다.
# so 라이브러리를 생성할 경우 (기본 STATIC 이다.)
# add_library(applib SHARED foo.cpp)
add_library(${PROJECT_NAME} foo.cpp)
