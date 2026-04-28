cmake_minimum_required(VERSION 3.8)

set(This ExampleTests)

set(Sources
    ExampleTests.cpp
)

add_executable(${This} ${Sources})

target_link_libraries(${This} PRIVATE Example)

# 🔥 FORCE CONSOLE MODE (THIS FIXES YOUR ERROR)
set_target_properties(${This} PROPERTIES LINK_FLAGS "-mconsole")

add_test(
    NAME ${This}
    COMMAND ${This}
)
