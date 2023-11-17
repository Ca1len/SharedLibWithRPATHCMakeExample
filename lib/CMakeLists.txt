project(dyn_lib)


add_library(${PROJECT_NAME} SHARED "console.cpp")
target_include_directories(${PROJECT_NAME} PUBLIC .)
