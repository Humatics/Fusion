add_executable(Advanced-Example main.c)

target_link_libraries(Advanced-Example PRIVATE Fusion)
target_include_directories(Advanced-Example PRIVATE
  ${PROJECT_SOURCE_DIR}/Fusion/include)
