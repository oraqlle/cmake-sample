# Tests need to be added as executables first
add_executable(test-phraseslib phraseslib.test.cxx)

# I'm using C++17 in the test
target_compile_features(test-phraseslib PRIVATE cxx_std_17)

# Should be linked to the main library, as well as the Catch2 testing library
target_link_libraries(test-phraseslib PRIVATE utils phrases Catch2::Catch2)

# If you register a test, then ctest and make test will run it.
# You can also run examples and check the output, as well.
add_test(NAME test-phraseslib-test COMMAND test-phraseslib) # Command can be a target
