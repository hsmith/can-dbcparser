cmake_minimum_required( VERSION 2.8.12 )

set( CANDBC_INCLUDE_DIR "${CMAKE_CURRENT_LIST_DIR}/header" )
include_directories( ${CANDBC_INCLUDE_DIR} )
add_library(
                dbcparser
                  ${CMAKE_CURRENT_LIST_DIR}/dbciterator.cpp
                  ${CMAKE_CURRENT_LIST_DIR}/message.cpp
                  ${CMAKE_CURRENT_LIST_DIR}/signal.cpp
              )

set( CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11" )

add_executable(
    dbcparser_example
      ${CMAKE_CURRENT_LIST_DIR}/main.cpp
  )


target_link_libraries( dbcparser_example PUBLIC dbcparser )