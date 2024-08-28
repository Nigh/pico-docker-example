add_executable(blink_simple
        blink_simple.c
)

# pull in common dependencies
target_link_libraries(blink_simple pico_stdlib)

# create map/bin/hex/uf2 file etc.
pico_add_extra_outputs(blink_simple)
