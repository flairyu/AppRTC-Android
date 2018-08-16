cmake_minimum_required(VERSION 3.4.1)

set(ENABLE_STATIC TRUE)

# add_subdirectory(${WEBRTC_REPO}/third_party/boringssl/src third_party/boringssl.out)
# add_subdirectory(${WEBRTC_REPO}/third_party/libjpeg_turbo third_party/libjpeg_turbo.out)
# add_subdirectory(${WEBRTC_REPO}/third_party/libyuv third_party/libyuv.out)
# add_subdirectory(${WEBRTC_REPO}/third_party/usrsctp/usrsctplib third_party/usrsctp.out)

add_subdirectory(abseil-cpp)
add_subdirectory(jsoncpp)
add_subdirectory(libevent)
add_subdirectory(libsrtp)
add_subdirectory(libvpx)
add_subdirectory(libyuv)
add_subdirectory(opus)
add_subdirectory(protobuf)
add_subdirectory(rnnoise)
add_subdirectory(usrsctp)
