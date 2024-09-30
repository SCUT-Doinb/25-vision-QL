# 在此处进行 CMake 设置（最小版本号，项目名）
cmake_minimum_required(VERSION 3.10)

project(
  Test          # 设置项目名
  LANGUAGES CXX # 指定语言，未指定的语言将不参与构建，例如 test.c 文件
)

find_package(OpenCV REQUIRED)

include_directories(
  ${OpenCV_INCLUDE_DIRS}
  ${CMAKE_CURRENT_SOURCE_DIR}/modules/M1/include 
  ${CMAKE_CURRENT_SOURCE_DIR}/modules/M2/include
  ${CMAKE_CURRENT_SOURCE_DIR}/modules/A1/include
  ${CMAKE_CURRENT_SOURCE_DIR}/modules/A2/include
  ${CMAKE_CURRENT_SOURCE_DIR}/common/kalman/include
  ${CMAKE_CURRENT_SOURCE_DIR}/common/math/include
)

####### 以下禁止修改 #######
add_subdirectory(common)   #
add_subdirectory(modules)  #
####### 以上禁止修改 #######

# 在此处生成可执行程序
add_executable(
  test
  main.cpp
)
# 在此处链接库
target_link_libraries(
  test
  INTERFACE kalman 
  PUBLIC math 
  PUBLIC M1 
  PUBLIC M2 
)
