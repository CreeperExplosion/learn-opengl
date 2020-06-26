

file(
    GLOB CPP_FILE src/sandbox/*.cpp
    
    )
file(
    GLOB H_FILE src/src/*.h
    
    )



add_executable(
    game
    "${H_FILE}"
    "${CPP_FILE}"
)

target_link_libraries(
    game
    graphics
)