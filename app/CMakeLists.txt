project(app)

set(libdyn_BINARY_DIR "../lib/build")
set(libdyn_SOURCE_DIR "../lib")
set(CMAKE_INSTALL_RPATH_USE_LINK_PATH TRUE)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)
add_executable(${PROJECT_NAME} main.cpp)

target_include_directories(${PROJECT_NAME} PUBLIC ${CMAKE_SOURCE_DIR}/${libdyn_SOURCE_DIR})
set_target_properties(${PROJECT_NAME} PROPERTIES LINK_FLAGS "-Wl,-rpath,./")
target_link_libraries(${PROJECT_NAME} PUBLIC
    ${CMAKE_BINARY_DIR}/libdyn_lib.so)

configure_file(${CMAKE_SOURCE_DIR}/${libdyn_BINARY_DIR}/libdyn_lib.so
    ${CMAKE_BINARY_DIR}/libdyn_lib.so COPYONLY)
