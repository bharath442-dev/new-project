cmake_minimum_required(VERSION 3.8)

set(This ExampleTests)

set(Sources
    ExampleTests.cpp
)

# 🔥 IMPORTANT: use console explicitly
add_executable(${This} ${Sources})

target_link_libraries(${This} PRIVATE Example)

target_include_directories(${This} PRIVATE ${CMAKE_SOURCE_DIR})

# 🔥 FORCE console subsystem (THIS IS THE KEY FIX)
target_link_options(${This} PRIVATE -Wl,-subsystem,console)

add_test(
    NAME ${This}
    COMMAND ${This}
)
