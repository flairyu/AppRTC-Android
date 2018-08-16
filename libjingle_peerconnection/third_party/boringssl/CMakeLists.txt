cmake_minimum_required(VERSION 3.4.1)

set(can_use_assembler TRUE)
enable_language(ASM)
SET(CMAKE_ASM_SOURCE_FILE_EXTENSIONS S)
SET(CMAKE_ASM_OUTPUT_EXTENSION ".o" )
SET(CMAKE_ASM_COMPILE_OBJECT "<CMAKE_ASM_COMPILER> -o <OBJECT> <SOURCE>")

file(GLOB_RECURSE src_boringssl
        ${WEBRTC_REPO}/third_party/boringssl/linux-aarch64/*.S
        ${WEBRTC_REPO}/third_party/boringssl/src/*.c
        ${WEBRTC_REPO}/third_party/boringssl/src/*.cc
        )
list(FILTER src_boringssl EXCLUDE REGEX ${TEST_CC_FILTER})
list(FILTER src_boringssl EXCLUDE REGEX 
        ".*/fuzz/.*|.*/googletest/.*")

add_library(boringssl STATIC
        ${src_boringssl}
        )
