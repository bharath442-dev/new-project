set(This ExampleTests)

set(Sources
    ExampleTests.cpp
)

# 🔥 IMPORTANT CHANGE HERE
add_executable(${This} ${Sources})

target_link_libraries(${This} PRIVATE Example)

# ✅ FORCE console subsystem (this is the real fix)
set_target_properties(${This} PROPERTIES
    LINK_FLAGS "-mconsole"
)

add_test(
    NAME ${This}
    COMMAND ${This}
)
