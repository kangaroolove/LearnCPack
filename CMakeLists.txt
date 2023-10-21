cmake_minimum_required(VERSION 3.5)

project(LearnCPack VERSION 0.1 LANGUAGES CXX)

set(CMAKE_INCLUDE_CURRENT_DIR ON)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

include_directories(
)

list(APPEND EXTRA_LIBS 
)

set(PROJECT_SOURCES
    main.cpp
)

set(PROJECT_UIS
)

set(PROJECT_RESOURCES
)

add_executable(${PROJECT_NAME} 
	${PROJECT_SOURCES}
	${PROJECT_UIS}
	${PROJECT_RESOURCES}
)

target_link_libraries(${PROJECT_NAME} ${EXTRA_LIBS})

install(TARGETS ${PROJECT_NAME} RUNTIME DESTINATION bin)
include(CPack)