add_library(mod_openexr MODULE
        "${CMAKE_CURRENT_LIST_DIR}/trgt_openexr.cpp"
        "${CMAKE_CURRENT_LIST_DIR}/main.cpp"
        "${CMAKE_CURRENT_LIST_DIR}/mptr_openexr.cpp"
)

message(STATUS "OpenEXR include: ${OPENEXR_INCLUDE_DIRS}")

target_include_directories(mod_openexr SYSTEM PRIVATE ${OPENEXR_INCLUDE_DIRS})

target_link_libraries(mod_openexr synfig ${OPENEXR_LIBRARIES})

install (
    TARGETS mod_openexr
    DESTINATION lib/synfig/modules
)
