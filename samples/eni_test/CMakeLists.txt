include(AddENI)
get_filename_component(TARGET_NAME ${CMAKE_CURRENT_SOURCE_DIR} NAME)

add_executable(${TARGET_NAME} ${TARGET_NAME}.c)

add_eni(${TARGET_NAME}
  sample-eni.xml
)
if ( Xenomai_FOUND )
    xenomai_target_bootstrap(${TARGET_NAME} SKINS posix)
endif()
target_link_libraries(${TARGET_NAME} PRIVATE soem)
install(TARGETS ${TARGET_NAME} DESTINATION bin)