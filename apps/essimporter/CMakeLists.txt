set(ESSIMPORTER_FILES
    main.cpp
    importer.cpp
    importplayer.cpp
    importnpcc.cpp
    importcrec.cpp
    importcellref.cpp
    importacdt.cpp
    importinventory.cpp
    importklst.cpp
    importcntc.cpp
    importercontext.cpp
    converter.cpp
    convertacdt.cpp
    convertnpcc.cpp
    convertinventory.cpp
    convertcrec.cpp
    convertcntc.cpp
)

add_executable(openmw-essimporter
    ${ESSIMPORTER_FILES}
)

target_link_libraries(openmw-essimporter
    ${Boost_LIBRARIES}
    components
)

if (BUILD_WITH_CODE_COVERAGE)
  add_definitions (--coverage)
  target_link_libraries(openmw-essimporter gcov)
endif()
