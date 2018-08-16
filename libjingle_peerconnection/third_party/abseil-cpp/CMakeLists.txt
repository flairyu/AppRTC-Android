cmake_minimum_required(VERSION 3.4.1)

include_directories(
    ${WEBRTC_REPO}/third_party/abseil-cpp
)

file(GLOB_RECURSE src_absl
    ${WEBRTC_REPO}/third_party/abseil-cpp/absl/base/*.cc
    ${WEBRTC_REPO}/third_party/abseil-cpp/absl/types/*.cc
)
list(FILTER src_absl EXCLUDE REGEX ${TEST_CC_FILTER})
list(FILTER src_absl EXCLUDE REGEX 
    ".*_benchmark.cc|.*_testing.cc")

add_library(absl STATIC
    ${src_absl}
)
