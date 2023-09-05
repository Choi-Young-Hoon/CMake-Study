# 현재 CMake 스크립트를 사용하는데 최소한의 버전을 명시한다.
cmake_minimum_required(VERSION 3.0)

# 프로젝트 명과 C++을 사용한다고 명시한다. 
project(hello_world CXX)

# 해당 프로젝트에서 사용될 C++ 버전을 17로 지정한다.
set(CMAKE_CXX_STANDARD 17)

# CMake에서 target_include_directories()는 특정 대상에 대해서만 포함 디렉토리를 추가하는 반면, 
# include_directories()는 현재 디렉토리와 하위 디렉토리에 있는 모든 대상에 대해 포함 디렉토리를 추가합니다
# include_directories()는 전역 include 경로 설정
# include_directories(${PROJECT_SOURCE_DIR}/include/hello2) 

# 서브 디렉토리의 CMakeLists.txt를 수행함
add_subdirectory(lib)

