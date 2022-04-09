cmake_minimum_required(VERSION 3.21)
project(Phantom_Injector)

set(CMAKE_CXX_STANDARD 14)

find_package(SDL2 REQUIRED)
find_package(OpenGL REQUIRED)

include_directories(${SDL2_INCLUDE_DIRS} ${OPENGL_INCLUDE_DIR} src/imgui src/ImGuiFileDialog)
link_libraries(${SDL2_LIBRARIES} ${OPENGL_gl_LIBRARY} OpenGL::GL)

set(IMGUI_SOURCE_FILES src/imgui/imgui.cpp src/imgui/imgui_impl_opengl3.cpp src/imgui/imgui_impl_sdl.cpp src/imgui/imgui_draw.cpp src/imgui/imgui_tables.cpp src/imgui/imgui_widgets.cpp src/imgui/imgui_demo.cpp)
set(FILE_DIALOG_SOURCE_FILES src/ImGuiFileDialog/ImGuiFileDialog.cpp)

add_executable(Phantom_Injector src/main.cpp ${IMGUI_SOURCE_FILES} ${FILE_DIALOG_SOURCE_FILES})
