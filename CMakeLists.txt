cmake_minimum_required(VERSION 3.14)
project(hello)

set(CMAKE_CXX_STANDARD 14)
set(SRC_FILES
	main.cpp
        )
set(CLANG_INC_DIR usr/local/include)
set(CLANG_LINK_DIR usr/local/lib)

set(CMAKE_BUILD_TYPE "Release")

add_compile_options(-O3)


include_directories(${CLANG_INC_DIR})
link_directories(${CLANG_LINK_DIR})

add_executable(hello ${SRC_FILES})


target_link_libraries(hello
        clangAST
        clangBasic
        clangDriver
        clangFrontend
        clangSerialization
        clangStaticAnalyzerFrontend
        clangTooling
        )
