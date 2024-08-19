cmake_minimum_required(VERSION 3.29.2)

project(mainwindowDemo)

# 设置C++标准（可选，但推荐）  
set(CMAKE_PREFIX_PATH $ENV{Qt_DIR})
set(CMAKE_CXX_STANDARD 11)  
set(CMAKE_CXX_STANDARD_REQUIRED ON)  

set(CMAKE_AUTOUIC ON)
set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)


set(CMAKE_AUTOUIC_SEARCH_PATHS "ui")

find_package(Qt5 COMPONENTS Core Widgets REQUIRED)

# file(GLOB_RECURSE PROJECT_SOURCE
#     "*.cpp" "*.h" "*.ui"
# )


set(PROJECT_SOURCE 
mainwindow.h
mainwindow.cpp
ui/mainwindow.ui
main.cpp
)

add_executable(${PROJECT_NAME} ${PROJECT_SOURCE})


target_link_libraries(${PROJECT_NAME} PRIVATE  Qt5::Core Qt5::Widgets)

