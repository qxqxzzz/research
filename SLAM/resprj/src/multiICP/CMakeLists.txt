MESSAGE(STATUS ${CSPARSE_INCLUDE_DIR})
INCLUDE_DIRECTORIES(${G2O_INCLUDE_DIR} ${EIGEN3_INCLUDE_DIR} ${CSPARSE_INCLUDE_DIR} ${PCL_INCLUDE_DIRS})

ADD_EXECUTABLE(multiICP multiICP.cpp)
FIND_PACKAGE( OpenCV REQUIRED )
TARGET_LINK_LIBRARIES(multiICP ${PCL_LIBRARIES} ${OpenCV_LIBS} g2o_core g2o_types_slam3d g2o_solver_csparse g2o_stuff g2o_csparse_extension pthread ${CSPARSE_LIBRARY})
