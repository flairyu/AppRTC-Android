cmake_minimum_required(VERSION 3.4.1)

include_directories(
    ${WEBRTC_REPO}/third_party/libyuv/include
    ${WEBRTC_REPO}/third_party/protobuf/src
)

file(GLOB_RECURSE src_yuv
    ${WEBRTC_REPO}/third_party/libyuv/source/*.cc
)

add_library(yuv STATIC
    ${src_yuv}
)
