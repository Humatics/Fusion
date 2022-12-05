add_executable(Simple-Example main.c)

target_link_libraries(Simple-Example PRIVATE Fusion)
target_include_directories(Simple-Example PRIVATE
  ${PROJECT_SOURCE_DIR}/Fusion/include)
