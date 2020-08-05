
set(SOURCES eepromtool.c)
add_executable(eepromtool ${SOURCES})
target_link_libraries(eepromtool ${SOEM_LIB_NAME})
install(TARGETS eepromtool DESTINATION bin)
