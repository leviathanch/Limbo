project(gzstream)

include_directories(
  ${CMAKE_CURRENT_SOURCE_DIR}
  ${ZLIB_INCLUDE_DIRS}
  )
set(CMAKE_POSITION_INDEPENDENT_CODE ON)

add_library(${PROJECT_NAME} SHARED ${CMAKE_CURRENT_SOURCE_DIR}/gzstream.C)
target_link_libraries(${PROJECT_NAME} ${ZLIB_LIBRARIES})

if(INSTALL_LIMBO)
    install(TARGETS ${PROJECT_NAME} DESTINATION ${LIMBO_LIBDIR})
    install(FILES ${CMAKE_CURRENT_SOURCE_DIR}/gzstream.h DESTINATION include/limbo/thirdparty/${PROJECT_NAME})
endif(INSTALL_LIMBO)
