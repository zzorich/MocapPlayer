cmake_minimum_required(VERSION 3.0)
project(KeyFraming)

set(PLAYER_OBJECT_FILES
        displaySkeleton.cpp
        interface.cpp
        motion.cpp
        posture.cpp
        skeleton.cpp
        transform.cpp
        vector.cpp
        mocapPlayer.cpp
        ppm.cpp
        pic.cpp
        performanceCounter.cpp
)
set(INTERPOLATE_OBJECT_FILES
        motion.cpp
        posture.cpp
        skeleton.cpp
        transform.cpp
        vector.cpp
        interpolator.cpp
        quaternion.cpp
        interpolate.cpp
)

find_package(FLTK REQUIRED)
include_directories(${FLTK_INCLUDE_DIR})

add_executable(mocapPlayer ${PLAYER_OBJECT_FILES})
target_link_libraries(mocapPlayer ${FLTK_LIBRARIES})

add_executable(interpolate ${INTERPOLATE_OBJECT_FILES})
target_link_libraries(interpolate ${FLTK_LIBRARIES})