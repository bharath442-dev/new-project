cmake_minimum_required(VERSION 3.8)

set(This ExampleTests)

set(Sources
    ExampleTests.cpp
)

add_executable(${This} ${Sources})
target_link_options(${This} PRIVATE -mconsole)

target_link_libraries(${This} PRIVATE Example)

add_test(
    NAME ${This}
    COMMAND ${This}
)
