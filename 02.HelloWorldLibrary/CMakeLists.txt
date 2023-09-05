# 여러 소스를 빌드하기 위해서는 add_library()로 먼저 라이브러리를 생성 후 
# target_link_libraries()를 사용하여 링크한다.

# 현재 CMake 스크립트를 사용하는데 최소한의 버전을 명시한다.
cmake_minimum_required(VERSION 2.4)

# 프로젝트 명과 C++을 사용한다고 명시한다. 
project(hello_world CXX)

# 해당 프로젝트에서 사용될 C++ 버전을 17로 지정한다.
set(CMAKE_CXX_STANDARD 17)

# include 디렉토리를 지정한다.
# PROJECT_SOURCE_DIR 은 현재 디렉토리 범위 또는 그 부모 디렉토리에서
# 가장 최근에 project() 함수를 호출했을 때의 소스 디렉토리다.
include_directories(${PROJECT_SOURCE_DIR})

# add_library(<name> STATIC|SHARED source) sources 파일들에 대한 라이브러리를 생성한다.
# so 라이브러리를 생성할 경우 (기본 STATIC 이다.)
# add_library(applib SHARED foo.cpp)
add_library(applib STATIC foo.cpp)

# # 실행 파일인 app을 main.cpp로부터 생성
add_executable(app main.cpp)

# applib와 app을 링크한다.
target_link_libraries(app applib)

