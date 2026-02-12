set(TARGET sd-server)

add_executable(${TARGET} main.cpp)
install(TARGETS ${TARGET} RUNTIME)
target_link_libraries(${TARGET} PRIVATE stable-diffusion ${CMAKE_THREAD_LIBS_INIT})
target_compile_features(${TARGET} PUBLIC c_std_11 cxx_std_20)
if (MSVC)
    target_compile_options(${TARGET} PUBLIC "/Zc:__cplusplus")
endif()