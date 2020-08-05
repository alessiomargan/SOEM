
set(SOURCES slaveinfo.c)
add_executable(slaveinfo ${SOURCES})
if ( Xenomai_FOUND )
    xenomai_target_bootstrap(slaveinfo
        SKINS posix
    )
endif()
target_link_libraries(slaveinfo PRIVATE ${SOEM_LIB_NAME})
install(TARGETS slaveinfo DESTINATION bin)
