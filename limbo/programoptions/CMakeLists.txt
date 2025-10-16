include_directories(
    ${PROJECT_SOURCE_DIR}
    )
add_library(programoptions ProgramOptions.cpp)
if(INSTALL_LIMBO)
    install(TARGETS programoptions DESTINATION ${LIMBO_LIBDIR})
endif(INSTALL_LIMBO)

file(GLOB SOURCES
    *.h
    )
if(INSTALL_LIMBO)
    install(FILES ${SOURCES} DESTINATION include/limbo/programoptions)
endif(INSTALL_LIMBO)
