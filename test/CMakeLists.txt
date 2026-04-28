cmake_minimum_required(VERSION 3.8)

set(This ExampleTests)

set(Sources
    ExampleTests.cpp
)

add_executable(${This} ${Sources})

target_link_libraries(${This} PRIVATE Example)

# 🔥 ADD THIS LINE (IMPORTANT FIX)
target_include_directories(${This} PRIVATE ${CMAKE_SOURCE_DIR})

add_test(
    NAME ${This}
    COMMAND ${This}
)
