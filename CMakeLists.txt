cmake_minimum_required(VERSION 3.12)
set(CMAKE_CXX_STANDARD 14)

project(test_qt)

include_directories(include)
aux_source_directory(src SOURCE_FILES)

# qt

# Find includes in corresponding build directories
set(CMAKE_INCLUDE_CURRENT_DIR ON)
# Instruct CMake to run moc automatically when needed
set(CMAKE_AUTOMOC ON)
# Create code from a list of Qt designer ui files
set(CMAKE_AUTOUIC ON)

# Find the QtWidgets library
set(CMAKE_PREFIX_PATH G:\\qt5\\5.10.0\\mingw53_32\\lib\\cmake)
find_package(Qt5 REQUIRED Widgets)

# vtk
set(VTK_DIR G:\\VTK)
find_package(VTK REQUIRED)
include(${VTK_USE_FILE})


set(QT_FORM_FILES include/mainwindow.h include/ui_mainwindow.h)

add_executable(${PROJECT_NAME} WIN32 ${SOURCE_FILES} ${QT_FORM_FILES})

# Use the Widgets module from Qt 5
target_link_libraries(${PROJECT_NAME} Qt5::Widgets ${VTK_LIBRARIES})
