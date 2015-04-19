cmake_minimum_required(VERSION 3.0)


project(uMachine)


add_subdirectory(machine)

add_executable(execute ucode.cpp)

target_link_libraries(execute machine)

install(TARGETS execute DESTINATION bin)



include_directories(${CMAKE_CURRENT_SOURCE_DIR}/machine/)


