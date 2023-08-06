cmake_minimum_required(VERSION 3.5)

set(CMAKE_CXX_STANDARD 17)
find_package(Eigen3 REQUIRED)
find_package(GLEW REQUIRED)
if (UNIX)
    set(OpenGL_GL_PREFERENCE LEGACY)
endif ()
find_package(OpenGL REQUIRED)
find_package(glfw3 REQUIRED)
find_package(OpenCV REQUIRED)
find_package(OpenMP REQUIRED)
include_directories(
  SYSTEM
  /usr/include/eigen3
  /usr/local/include/opencv4)

add_executable(evaluate_rbot_dataset evaluate_rbot_dataset.cpp rbot_evaluator.cpp rbot_evaluator.h)
target_link_libraries(evaluate_rbot_dataset PUBLIC m3t
  ${OpenCV_LIBS} stdc++fs GLEW glfw3 GL GLU dl pthread X11 gomp)

add_executable(parameter_study_rbot_dataset parameter_study_rbot_dataset.cpp rbot_evaluator.cpp rbot_evaluator.h)
target_link_libraries(parameter_study_rbot_dataset PUBLIC m3t
  ${OpenCV_LIBS} stdc++fs GLEW glfw3 GL GLU dl pthread X11 gomp)

add_executable(evaluate_choi_dataset evaluate_choi_dataset.cpp choi_evaluator.cpp choi_evaluator.h)
target_link_libraries(evaluate_choi_dataset PUBLIC m3t
  ${OpenCV_LIBS} stdc++fs GLEW glfw3 GL GLU dl pthread X11 gomp)

add_executable(parameter_study_choi_dataset parameter_study_choi_dataset.cpp choi_evaluator.cpp choi_evaluator.h)
target_link_libraries(parameter_study_choi_dataset PUBLIC m3t
  ${OpenCV_LIBS} stdc++fs GLEW glfw3 GL GLU dl pthread X11 gomp)

add_executable(evaluate_opt_dataset evaluate_opt_dataset.cpp opt_evaluator.cpp opt_evaluator.h)
target_link_libraries(evaluate_opt_dataset PUBLIC m3t
  ${OpenCV_LIBS} stdc++fs GLEW glfw3 GL GLU dl pthread X11 gomp)

add_executable(parameter_study_opt_dataset parameter_study_opt_dataset.cpp opt_evaluator.cpp opt_evaluator.h)
target_link_libraries(parameter_study_opt_dataset PUBLIC m3t
  ${OpenCV_LIBS} stdc++fs GLEW glfw3 GL GLU dl pthread X11 gomp)

add_executable(evaluate_ycb_dataset evaluate_ycb_dataset.cpp ycb_evaluator.cpp ycb_evaluator.h)
target_link_libraries(evaluate_ycb_dataset PUBLIC m3t
  ${OpenCV_LIBS} stdc++fs GLEW glfw3 GL GLU dl pthread X11 gomp)

add_executable(parameter_study_ycb_dataset parameter_study_ycb_dataset.cpp ycb_evaluator.cpp ycb_evaluator.h)
target_link_libraries(parameter_study_ycb_dataset PUBLIC m3t
  ${OpenCV_LIBS} stdc++fs GLEW glfw3 GL GLU dl pthread X11 gomp)

add_executable(evaluate_rtb_dataset evaluate_rtb_dataset.cpp rtb_evaluator.cpp rtb_evaluator.h)
target_link_libraries(evaluate_rtb_dataset PUBLIC m3t
  ${OpenCV_LIBS} stdc++fs GLEW glfw3 GL GLU dl pthread X11 gomp)

add_executable(parameter_study_rtb_dataset parameter_study_rtb_dataset.cpp rtb_evaluator.cpp rtb_evaluator.h)
target_link_libraries(parameter_study_rtb_dataset PUBLIC m3t
  ${OpenCV_LIBS} stdc++fs GLEW glfw3 GL GLU dl pthread X11 gomp)

add_executable(run_on_recorded_sequence run_on_recorded_sequence.cpp)
target_link_libraries(run_on_recorded_sequence PUBLIC m3t
  ${OpenCV_LIBS} stdc++fs GLEW glfw3 GL GLU dl pthread X11 gomp)

add_executable(run_generated_tracker run_generated_tracker.cpp)
target_link_libraries(run_generated_tracker PUBLIC m3t
  ${OpenCV_LIBS} stdc++fs GLEW glfw3 GL GLU dl pthread X11 gomp)

add_executable(run_pen_paper_demo run_pen_paper_demo.cpp)
target_link_libraries(run_pen_paper_demo PUBLIC m3t
  ${OpenCV_LIBS} stdc++fs GLEW glfw3 GL GLU dl pthread X11 gomp)

add_executable(constraint_convergence constraint_convergence.cpp)
target_link_libraries(constraint_convergence PUBLIC m3t
  ${OpenCV_LIBS} stdc++fs GLEW glfw3 GL GLU dl pthread X11 gomp)

add_executable(optimization_time optimization_time.cpp)
target_link_libraries(optimization_time PUBLIC m3t
  ${OpenCV_LIBS} stdc++fs GLEW glfw3 GL GLU dl pthread X11 gomp)

if (USE_AZURE_KINECT OR USE_REALSENSE)
    add_executable(record_camera_sequence record_camera_sequence.cpp)
    target_link_libraries(record_camera_sequence PUBLIC m3t
      ${OpenCV_LIBS} stdc++fs GLEW glfw3 GL GLU dl pthread X11 gomp)

    add_executable(run_on_camera_sequence run_on_camera_sequence.cpp)
    target_link_libraries(run_on_camera_sequence PUBLIC m3t
      ${OpenCV_LIBS} stdc++fs GLEW glfw3 GL GLU dl pthread X11 gomp)
endif ()
