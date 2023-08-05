CMAKE_MINIMUM_REQUIRED(VERSION 3.5)

# Options
# =============================================================================
if (USE_GTEST)

    # Libraries
    # =========================================================================
    find_package(GTest 1.7.0 REQUIRED)
    include_directories(SYSTEM ${GTEST_INCLUDE_DIRS} /usr/include/eigen3)

    # Define headers and sources
    # =========================================================================
    FILE(GLOB SOURCES "*.cpp")
    FILE(GLOB HEADERS "*.h")

    # Define target
    # =========================================================================
    add_executable(gtest_run ${SOURCES})
    target_link_libraries(gtest_run PUBLIC m3t ${GTEST_BOTH_LIBRARIES} ${OpenCV_LIBS} stdc++fs GLEW glfw3 GL GLU dl X11 gomp)
endif ()
