cmake_minimum_required(VERSION 3.5.0)
set(PROJECT_NAME bybit-exchange)
project(${PROJECT_NAME} VERSION 0.1.0 LANGUAGES C CXX)

find_package(CURL CONFIG REQUIRED)

file(GLOB_RECURSE BACKEND_SOURCES "src/backend/*.cpp" "backend/*.hpp")
file(GLOB_RECURSE FRONTEND_SOURCES "src/frontend/*.cpp" "frontend/*.hpp")
set(SOURCES ${BACKEND_SOURCES} ${FRONTEND_SOURCES})

add_executable(${PROJECT_NAME}  src/main.cpp ${SOURCES})

target_link_libraries(${PROJECT_NAME} CURL::libcurl)

