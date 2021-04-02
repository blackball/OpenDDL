add_executable(Example Example.cpp)
target_link_libraries(Example PRIVATE OpenDDL)
target_compile_options(Example PRIVATE
     $<$<OR:$<CXX_COMPILER_ID:Clang>,$<CXX_COMPILER_ID:AppleClang>,$<CXX_COMPILER_ID:GNU>>:
     -Wall -Wno-multichar>
     $<$<CXX_COMPILER_ID:MSVC>:
     /W4>)
