add_executable(infix_trieste
  reader.cc
  infix_trieste.cc
  parse.cc
  )

target_link_libraries(infix_trieste
  trieste::trieste
)
 
add_test(NAME infix COMMAND infix_trieste test -f)

add_executable(infix
  reader.cc
  writers.cc
  infix.cc
  parse.cc
)

target_link_libraries(infix
  trieste::trieste
)

install(TARGETS infix infix_trieste RUNTIME DESTINATION infix)
install(DIRECTORY examples DESTINATION infix)
