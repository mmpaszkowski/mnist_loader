cmake_minimum_required(VERSION 3.0)

add_executable(mnist_example main.cpp)
target_compile_features(mnist_example PRIVATE cxx_range_for)
target_link_libraries(mnist_example mmpaszkowski::${PROJECT_NAME})
