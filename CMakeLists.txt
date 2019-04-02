cmake_minimum_required(VERSION "3.0.0")

project("PongClone")

add_executable("${PROJECT_NAME}" "Main.cpp")

set_target_properties("${PROJECT_NAME}" PROPERTIES CXX_STANDARD 14)

find_package(SFML 2 COMPONENTS system window graphics network audio REQUIRED)
find_package(tgui REQUIRED)
target_link_libraries("${PROJECT_NAME}" PRIVATE sfml-system sfml-window sfml-graphics sfml-network sfml-audio tgui)
