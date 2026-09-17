cmake_minimum_required(VERSION 3.10)
project(ClassroomAssignments C)

# Find all .c files in any directory starting with "week"
file(GLOB_RECURSE C_FILES "week*/*.c")

# Loop through each file found
foreach(C_FILE IN LISTS C_FILES)
    # Extract the filename without the .c extension (e.g., "my_name" from "my_name.c")
    get_filename_component(TARGET_NAME ${C_FILE} NAME_WE)

    # Create a run configuration for that specific file
    add_executable(${TARGET_NAME} ${C_FILE})
endforeach()