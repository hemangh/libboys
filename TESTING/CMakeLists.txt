# Add an executable target that uses the library
add_executable(boys_test boys_test.f90)
target_link_libraries(boys_test PRIVATE boys_func)

# Copy benchmark.values to the build directory
configure_file(${CMAKE_CURRENT_SOURCE_DIR}/benchmark.values ${CMAKE_CURRENT_BINARY_DIR}/benchmark.values COPYONLY)

#Add a custom target to run the executable as a test
add_custom_target(run_test
    COMMAND boys_test
    WORKING_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}
    COMMENT "Running tests..."
)

# Add the test
add_test(NAME Test_Boys COMMAND boys_test WORKING_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR})
