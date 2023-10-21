cmake_minimum_required(VERSION 3.5)

project(LearnCPack VERSION 1.0 LANGUAGES CXX)

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




#set(CPACK_GENERATOR NSIS)
set(CPACK_NSIS_PACKAGE_NAME ${PROJECT_NAME})
set(CPACK_NSIS_DISPLAY_NAME ${PROJECT_NAME})
set(EXE_TARGET_NAME ${CMAKE_SOURCE_DIR}/bin/LearnCPack.exe)
set(EWS_APP_NAME ${PROJECT_NAME})

set(CPACK_PACKAGE_EXECUTABLES "${EXE_TARGET_NAME}" "${EWS_APP_NAME}")
# install ico
set (CPACK_NSIS_MUI_ICON "${CMAKE_SOURCE_DIR}/res/LearnCPack.ico")
# uninstall ico
set (CPACK_NSIS_MUI_UNIICON "${CMAKE_SOURCE_DIR}/res/LearnCPack.ico")
# License ico
set (CPACK_PACKAGE_ICO "${CMAKE_SOURCE_DIR}/res/LearnCPack.bmp")
# License text
set (CPCK_RESOURCE_FILE_LICENSE "${CMAKE_SOURCE_DIR}/res/Copyright.txt")

# message("AAAAAAAAAAAAAAAAAAAAa")
# message(${CPACK_NSIS_PACKAGE_NAME})
# message(${CMAKE_SOURCE_DIR})

# set (CPACK_NSIS_MODIFY_PATH "ON")
# add/remove programs icon using an installed executat
# set (CPACK_NSIS_INSTALLED_ICON_NAME "${CMAKE_SOURCE_DIR}/bin/LearnCPack.exe")


set(CPACK_NSIS_EXTRA_INSTALL_COMMANDS "
    CreateShortCut \\\"$DESKTOP\\\\${EWS_APP_NAME}.lnk\\\" \\\"$INSTDIR\\\\bin\\\\${EWS_APP_NAME}\\\"
")


include(CPack)