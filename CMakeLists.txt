cmake_minimum_required(VERSION 3.9)
project(example VERSION 1.0.0 LANGUAGES CXX C)

find_package(irkit REQUIRED)

# Just to show what variables are available.
# Can and probably should be safely removed in your actual project.
get_cmake_property(_variableNames VARIABLES)
list (SORT _variableNames)
foreach (_variableName ${_variableNames})
    message(STATUS "${_variableName}=${${_variableName}}")
endforeach()

add_executable(app src/app.cpp)
target_link_libraries(app irkit)
target_compile_features(app PRIVATE cxx_std_17)
