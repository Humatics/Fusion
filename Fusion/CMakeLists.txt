file(GLOB_RECURSE files "./src/*.c")
include_directories(include)
add_library(Fusion ${files})
if(UNIX AND NOT APPLE)
    target_link_libraries(Fusion m) # link math library for Linux
endif()
set(CMAKE_INSTALL_PREFIX /usr/local)
install(TARGETS Fusion DESTINATION lib/Fusion EXPORT FusionTargets)
install(EXPORT FusionTargets DESTINATION lib/Fusion)
include(CMakePackageConfigHelpers)
write_basic_package_version_file(
  "FusionConfigVersion.cmake"
  VERSION 1.0.6
  COMPATIBILITY AnyNewerVersion
  )


install(FILES ${PROJECT_SOURCE_DIR}/FusionConfig.cmake
  ${PROJECT_SOURCE_DIR}/build/Fusion/FusionConfigVersion.cmake
  DESTINATION lib/Fusion)
