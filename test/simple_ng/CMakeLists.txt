set(SOURCES simple_ng.c)
add_executable(simple_ng ${SOURCES})
if ( Xenomai_FOUND )
    xenomai_target_bootstrap(simple_ng
        SKINS posix
    )
endif()
target_link_libraries(simple_ng PRIVATE ${SOEM_LIB_NAME})
install(TARGETS simple_ng DESTINATION bin)
