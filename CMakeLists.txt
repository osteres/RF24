cmake_minimum_required(VERSION 3.3)
# Some cutoms functions
include(./cmake/functions.txt)

# Library name
set(NAME RF24)

# Files
file(GLOB_RECURSE FILES_CPP "*.cpp")
file(GLOB_RECURSE FILES_H "*.h")
# Ignore some files
include(./cmake/ignore.txt)

# Define library
project("lib${NAME}")
add_library(${NAME} ${FILES_CPP} ${FILES_H})

# Permit to include files (similar as defining ./ directory to include path)
target_include_directories(${NAME} PUBLIC .)
