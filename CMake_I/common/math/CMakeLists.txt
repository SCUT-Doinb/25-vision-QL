aux_source_directory(src math_dir)

add_library(math STATIC ${math_dir})

target_include_directories(
    math 
    PUBLIC include
)

target_link_libraries(
    math 
    PUBLIC ${OpenCV_LIBS}
)