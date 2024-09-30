aux_source_directory(src A1_dir)

add_library(A1 STATIC ${A1_dir})

target_include_directories(
    A1
    PUBLIC include
)