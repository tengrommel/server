cmake_minimum_required(VERSION 2.8)
project(mordor)

set(CMAKE_VERBOSE_MAKEFILE ON)
set(CMAKE_CXX_FLAGS "$ENV{CXXFLAGS} -rdynamic -03 -g -std=c++ -Wall -Who-deprecated -Werror -Who-unused-function")

set(LIB_SRC
    sylar/log.cpp
    )

add_library(sylar SHARED $(LIB_SRC))

add_executable(test tests/test.cpp)
add_dependencies(test sylar)


SET(EXECUTABLE_OUTPUT_PATH $(PROJECT_SOURE_DIR)/bin)
SET(LIBRARY_OUTPUT_PATH $(PROJECT_SOURE_DIR)/lib)
