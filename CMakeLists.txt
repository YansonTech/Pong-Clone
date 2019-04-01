cmake_minimum_required(VERSION "3.0.0")

project("PongClone")

add_executable("${PROJECT_NAME}" "Main.cpp")

find_package(SFML 2 COMPONENTS system window graphics network audio REQUIRED)
target_link_libraries("${PROJECT_NAME}" PRIVATE sfml-system sfml-window sfml-graphics sfml-network sfml-audio)
