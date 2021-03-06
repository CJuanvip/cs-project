file(GLOB srcs
        "${CMAKE_CURRENT_SOURCE_DIR}/src/*.cpp"
        "${CMAKE_CURRENT_SOURCE_DIR}/src/ast/*.cpp"
        "${CMAKE_CURRENT_SOURCE_DIR}/src/ast/extractors/*.cpp"
        "${CMAKE_CURRENT_SOURCE_DIR}/src/common/*.cpp"
        "${CMAKE_CURRENT_SOURCE_DIR}/src/pkb/*.cpp"
        "${CMAKE_CURRENT_SOURCE_DIR}/src/parser/*.cpp"
        "${CMAKE_CURRENT_SOURCE_DIR}/src/query_evaluator/*.cpp"
        "${CMAKE_CURRENT_SOURCE_DIR}/src/query_evaluator/utils/*.cpp"
        "${CMAKE_CURRENT_SOURCE_DIR}/src/query_evaluator/evaluator/*.cpp")
file(GLOB headers
        "${CMAKE_CURRENT_SOURCE_DIR}/src/*.h" "${CMAKE_CURRENT_SOURCE_DIR}/src/*.hpp"
        "${CMAKE_CURRENT_SOURCE_DIR}/src/ast/*.h" "${CMAKE_CURRENT_SOURCE_DIR}/src/ast/*.hpp"
        "${CMAKE_CURRENT_SOURCE_DIR}/src/ast/extractors/*.h" "${CMAKE_CURRENT_SOURCE_DIR}/src/ast/extractors/*.hpp"
        "${CMAKE_CURRENT_SOURCE_DIR}/src/common/*.h" "${CMAKE_CURRENT_SOURCE_DIR}/src/common/*.hpp"
        "${CMAKE_CURRENT_SOURCE_DIR}/src/pkb/*.h" "${CMAKE_CURRENT_SOURCE_DIR}/src/pkb/*.hpp"
        "${CMAKE_CURRENT_SOURCE_DIR}/src/parser/*.h" "${CMAKE_CURRENT_SOURCE_DIR}/src/parser/*.hpp"
        "${CMAKE_CURRENT_SOURCE_DIR}/src/query_evaluator/*.h" "${CMAKE_CURRENT_SOURCE_DIR}/src/query_evaluator/*.hpp}"
        "${CMAKE_CURRENT_SOURCE_DIR}/src/query_evaluator/utils/*.h" "${CMAKE_CURRENT_SOURCE_DIR}/src/query_evaluator/utils/*.hpp}"
        "${CMAKE_CURRENT_SOURCE_DIR}/src/query_evaluator/utils/*.h" "${CMAKE_CURRENT_SOURCE_DIR}/src/query_evaluator/evaluator/*.hpp}")
add_library(spa ${srcs} ${headers})
# this makes the headers accessible for other projects which uses spa lib
target_include_directories(spa
        PUBLIC
        ${CMAKE_CURRENT_SOURCE_DIR}/src
        ${CMAKE_CURRENT_SOURCE_DIR}/src/ast
        ${CMAKE_CURRENT_SOURCE_DIR}/src/ast/extractors
        ${CMAKE_CURRENT_SOURCE_DIR}/src/common
        ${CMAKE_CURRENT_SOURCE_DIR}/src/pkb
        ${CMAKE_CURRENT_SOURCE_DIR}/src/parser
        ${CMAKE_CURRENT_SOURCE_DIR}/src/query_evaluator
        ${CMAKE_CURRENT_SOURCE_DIR}/src/query_evaluator/utils)
