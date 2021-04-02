set(OpenDDL_INCLUDE_DIR ${CMAKE_CURRENT_LIST_DIR}/Code/)
file(GLOB OpenDDL_SRCS "${CMAKE_CURRENT_LIST_DIR}/Code/*.cpp")

add_library(OpenDDL ${OpenDDL_SRCS})
target_include_directories(OpenDDL PUBLIC ${OpenDDL_INCLUDE_DIR})
target_compile_options(OpenDDL PRIVATE
     $<$<OR:$<CXX_COMPILER_ID:Clang>,$<CXX_COMPILER_ID:AppleClang>,$<CXX_COMPILER_ID:GNU>>:
     -Wall -Wno-multichar>
     $<$<CXX_COMPILER_ID:MSVC>:
     /W4>)
   
