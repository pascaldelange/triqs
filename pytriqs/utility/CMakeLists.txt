
SET(PYTHON_SOURCES 
  ${CMAKE_CURRENT_SOURCE_DIR}/__init__.py
  ${CMAKE_CURRENT_SOURCE_DIR}/dichotomy.py
  ${CMAKE_CURRENT_SOURCE_DIR}/bisect.py
  ${CMAKE_CURRENT_SOURCE_DIR}/dist_on_nodes.py
  ${CMAKE_CURRENT_BINARY_DIR}/mpi.py
  ${CMAKE_CURRENT_BINARY_DIR}/mpi_mpi4py.py
  ${CMAKE_CURRENT_BINARY_DIR}/mpi_boost.py
  ${CMAKE_CURRENT_SOURCE_DIR}/redirect.py
)

install (FILES ${PYTHON_SOURCES} DESTINATION ${TRIQS_PYTHON_LIB_DEST}/utility)


