# CMakeLists for PackageKit-Qt lib extra modules

if (USE_QT5)
  set(LIBNAME "packagekit-qt5")
else ()
  set(LIBNAME "packagekit-qt2")
endif ()

configure_file(${CMAKE_CURRENT_SOURCE_DIR}/${LIBNAME}-config.cmake.in
  ${CMAKE_CURRENT_BINARY_DIR}/${LIBNAME}-config.cmake
  @ONLY
)
configure_file(${CMAKE_CURRENT_SOURCE_DIR}/packagekit-qt-config-version.cmake.in
  ${CMAKE_CURRENT_BINARY_DIR}/${LIBNAME}-config-version.cmake
  @ONLY
)

install(FILES ${CMAKE_CURRENT_BINARY_DIR}/${LIBNAME}-config.cmake
        ${CMAKE_CURRENT_BINARY_DIR}/${LIBNAME}-config-version.cmake
        DESTINATION ${CMAKE_INSTALL_LIBDIR}/cmake/${LIBNAME}/
)
