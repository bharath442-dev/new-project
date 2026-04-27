set(This ExampleTests)

set(Sources
    ExampleTests.cpp
)

add_executable(${This} ${Sources})

target_link_libraries(${This} PRIVATE Example)

# 🔥 ADD THIS LINE (IMPORTANT)
target_link_options(${This} PRIVATE -mconsole)

add_test(
    NAME ${This}
    COMMAND ${This}
)
