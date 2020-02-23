set(CMAKE_POSITION_INDEPENDENT_CODE ON)

set(utils_SRCS Regression.cpp SimplePeakFinder.cpp SimpleMinMaxPeakFinder.cpp
               PoseEstimation.cpp)

set(utils_HDRS
    Regression.h
    Convolution.h
    Convolution.hpp
    HistogramDistances.h
    HistogramDistances.hpp
    SimplePeakFinder.h
    SimpleMinMaxPeakFinder.h
    PoseEstimation.h)

add_library(utils STATIC ${utils_SRCS})

install(
  TARGETS utils
  RUNTIME DESTINATION bin
  LIBRARY DESTINATION lib/flirtlib
  ARCHIVE DESTINATION lib/flirtlib)

install(FILES ${utils_HDRS} DESTINATION include/flirtlib/utils)
