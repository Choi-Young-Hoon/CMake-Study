# 현재 CMake 스크립트를 사용하는데 최소한의 버전을 명시한다.
cmake_minimum_required(VERSION 2.4)

# 프로젝트 명과 C++을 사용한다고 명시한다. 
project(hello_world CXX)

add_executable(app main.cpp)

