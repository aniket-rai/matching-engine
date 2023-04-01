cmake_minimum_required(VERSION 3.23)

set(PROJECT_NAME "${CMAKE_PROJECT_NAME}_Test")
project(${PROJECT_NAME})

set(CMAKE_CXX_STANDARD 23)

include(FetchContent)
FetchContent_Declare(
  googletest
  GIT_REPOSITORY https://github.com/google/googletest.git
  GIT_TAG release-1.12.1
)

# For Windows: Prevent overriding the parent project's compiler/linker settings
if(WIN32)
	set(gtest_force_shared_crt ON CACHE BOOL "" FORCE)

FetchContent_MakeAvailable(googletest)
enable_testing()

file(GLOB_RECURSE SRC_FILES src/*.cpp src/*.h)
add_executable(${PROJECT_NAME} ${SRC_FILES})

target_link_libraries(
  ${PROJECT_NAME}
  GTest::gtest_main
)

include(GoogleTest)
gtest_discover_tests(${PROJECT_NAME})