find_package(TestCSimple)
enable_testing()

option (TESTS_C_WITH_VALGRIND "Run all the tests also through valgrind" OFF)

macro(all_tests )

 FILE(GLOB TestList RELATIVE ${CMAKE_CURRENT_SOURCE_DIR} *.cpp)
 FOREACH( TestName1  ${TestList} )
  STRING(REPLACE ".cpp" "" TestName ${TestName1})
  add_executable( ${TestName}  ${CMAKE_CURRENT_SOURCE_DIR}/${TestName}.cpp )
  add_test_C_simple( ${TestName}    )
  if (TESTS_C_WITH_VALGRIND)
   add_test ( ${TestName}_valgrind valgrind --error-exitcode=1 ${CMAKE_CURRENT_BINARY_DIR}/${TestName})
  endif()
 ENDFOREACH( TestName1  ${TestList} )

endmacro()

add_all_subdirectories_with_cmakelist()

