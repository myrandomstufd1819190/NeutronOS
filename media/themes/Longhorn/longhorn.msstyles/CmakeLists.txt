file(GLOB_RECURSE longhorn_rc_deps
    ${CMAKE_CURRENT_SOURCE_DIR}/bitmaps/*
    ${CMAKE_CURRENT_SOURCE_DIR}/lang/*
    ${CMAKE_CURRENT_SOURCE_DIR}/streams/*
    ${CMAKE_CURRENT_SOURCE_DIR}/resources/*
    ${CMAKE_CURRENT_SOURCE_DIR}/textfiles/*
    ${CMAKE_CURRENT_SOURCE_DIR}/variants/*)

add_rc_deps(longhorn.rc ${longhorn_rc_deps})

add_library(longhorn.msstyles MODULE longhorn.rc)
set_module_type(longhorn.msstyles module)
add_dependencies(longhorn.msstyles xdk)
set_target_properties(longhorn.msstyles PROPERTIES SUFFIX "")

add_cd_file(TARGET longhorn.msstyles DESTINATION reactos/Resources/Themes/Longhorn FOR all)
