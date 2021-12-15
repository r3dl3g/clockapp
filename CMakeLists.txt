cmake_minimum_required(VERSION 3.14 FATAL_ERROR)

project("ClockApp" CXX)

add_subdirectory(libs/guipp/gui gui)

add_definitions(${GUIPP_CXX_FLAGS})

include_directories(${PROJECT_BINARY_DIR} ${GUIPP_INCLUDE_DIRS})

add_executable(${PROJECT_NAME} ${PROJECT_NAME}.cpp)
target_link_libraries(${PROJECT_NAME} ${GUIPP_APP_LIBRARIES} ${GUIPP_SYS_LIBRARIES})
set_target_properties(${PROJECT_NAME} PROPERTIES CXX_STANDARD ${GUIPP_CXX_STANDARD})

install(TARGETS ${PROJECT_NAME})

