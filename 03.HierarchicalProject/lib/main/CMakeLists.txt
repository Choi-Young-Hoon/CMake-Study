# 현재 CMake 스크립트를 사용하는데 최소한의 버전을 명시한다.
cmake_minimum_required(VERSION 2.4)

# 프로젝트 명과 C++을 사용한다고 명시한다. 
project(mainapp CXX)

# 해당 프로젝트에서 사용될 C++ 버전을 17로 지정한다.
set(CMAKE_CXX_STANDARD 17)

# # 실행 파일인 app을 main.cpp로부터 생성
add_executable(${PROJECT_NAME} main.cpp)

# target_include_directories()는 PROJECT_NAME 프로젝트에 include 경로를 추가한다.
# CMAKE_SOURCE_DIR은 최정상위 CMakeLists.txt 파일이 있는 폴더의 경로를 가리킨다.
target_include_directories(${PROJECT_NAME}
PUBLIC
    ${CMAKE_SOURCE_DIR}/include/hello2
)

# hello2는 lib/hello2/CMakeLists.txt의 프로젝트 명이다. hello2의 라이브러리를 링크
target_link_libraries(${PROJECT_NAME}  hello2)

