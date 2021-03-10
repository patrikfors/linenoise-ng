cmake_minimum_required(VERSION 3.15)

add_executable(linenoise_example example.c)
target_link_libraries(linenoise_example PRIVATE linenoise)
