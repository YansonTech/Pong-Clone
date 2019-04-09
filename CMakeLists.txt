cmake_minimum_required(VERSION "3.0.0")

project("PongClone")

add_executable("${PROJECT_NAME}" "Main.cpp")

set_target_properties("${PROJECT_NAME}" PROPERTIES CXX_STANDARD 14)

find_package(SFML 2 COMPONENTS system window graphics network audio REQUIRED)
find_package(tgui REQUIRED)
target_link_libraries("${PROJECT_NAME}" PRIVATE sfml-system sfml-window sfml-graphics sfml-network sfml-audio tgui)

file(GLOB_RECURSE BOX2D_HEADER_FILES "${CMAKE_CURRENT_SOURCE_DIR}/Box2D/Box2D/*.h")
file(GLOB_RECURSE BOX2D_SOURCES_FILES "${CMAKE_CURRENT_SOURCE_DIR}/Box2D/Box2D/*.cpp")

target_sources("${PROJECT_NAME}" PRIVATE ${BOX2D_HEADER_FILES} ${BOX2D_SOURCES_FILES})

target_include_directories("${PROJECT_NAME}" PRIVATE "${CMAKE_CURRENT_SOURCE_DIR}/Box2D")
