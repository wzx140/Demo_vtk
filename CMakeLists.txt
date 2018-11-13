cmake_minimum_required(VERSION 3.12)
set(CMAKE_CXX_STANDARD 11)

project(Demo_vtk)

set(CMAKE_BUILD_TYPE Debug)

include_directories(include)
aux_source_directory(src SOURCE_FILES)
set(QT_FORM_FILES include/mainwindow.h src/mainwindow.ui)


#set root
set(Qt5_ROOT /opt/Qt5.11.2)
set(VTK_ROOT /opt/VTK/DEBUG)

# qt
# Find includes in corresponding build directories
set(CMAKE_INCLUDE_CURRENT_DIR ON)
# Instruct CMake to run moc automatically when needed
set(CMAKE_AUTOMOC ON)
# Create code from a list of Qt designer ui files
set(CMAKE_AUTOUIC ON)
# Find the QtWidgets library
find_package(Qt5 REQUIRED Widgets)

# vtk
find_package(VTK REQUIRED)
include(${VTK_USE_FILE})

add_executable(${PROJECT_NAME} WIN32 ${SOURCE_FILES} ${QT_FORM_FILES})

# Use the Widgets module from Qt 5
target_link_libraries(${PROJECT_NAME} Qt5::Widgets ${VTK_LIBRARIES})
