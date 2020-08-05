
set(SOURCES simple_test.c)
add_executable(simple_test ${SOURCES})
if ( Xenomai_FOUND )
    xenomai_target_bootstrap(simple_test
        SKINS posix
    )
endif()
target_link_libraries(simple_test PRIVATE ${SOEM_LIB_NAME})
install(TARGETS simple_test DESTINATION bin)
