# 현재 CMake 스크립트를 사용하는데 최소한의 버전을 명시한다.
cmake_minimum_required(VERSION 2.4)

# 프로젝트 명과 C++을 사용한다고 명시한다. 
project(hello_world CXX)

# 해당 프로젝트에서 사용될 C++ 버전을 17로 지정한다.
set(CMAKE_CXX_STANDARD 17)

# 실행 파일인 app을 main.cpp로부터 생성
add_executable(app main.cpp)

