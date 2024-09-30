aux_source_directory(src M2_dir)

add_library(M2 STATIC ${M2_dir})

target_include_directories(
    M2
    PUBLIC include
)

target_link_libraries(
    M2 
    PUBLIC A2
)