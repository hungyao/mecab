# Sets the minimum version of CMake required to build your native library.
# This ensures that a certain set of CMake features is available to
# your build.

cmake_minimum_required(VERSION 3.4.1)

# Specifies a library name, specifies whether the library is STATIC or
# SHARED, and provides relative paths to the source code. You can
# define multiple libraries by adding multiple add_library() commands,
# and CMake builds them for you. When you build your app, Gradle
# automatically packages shared libraries with your APK.

add_library(
    # Specifies the name of the library.
    mecab

    # Sets the library as a shared library.
    SHARED

    # Provides a relative path to your source file(s).
    src/viterbi.cpp
    src/tagger.cpp
    src/utils.cpp
    src/utils.h
    src/eval.cpp
    src/iconv_utils.cpp
    src/iconv_utils.h
    src/dictionary_rewriter.h
    src/dictionary_rewriter.cpp
    src/dictionary_generator.cpp
    src/dictionary_compiler.cpp
    src/context_id.h
    src/context_id.cpp
    src/winmain.h
    src/thread.h
    src/connector.cpp
    src/nbest_generator.h
    src/nbest_generator.cpp
    src/connector.h
    src/writer.h
    src/writer.cpp
    src/mmap.h
    src/ucs.h
    src/string_buffer.h
    src/string_buffer.cpp
    src/tokenizer.h
    src/stream_wrapper.h
    src/common.h
    src/darts.h
    src/char_property.h
    src/ucstable.h
    src/freelist.h
    src/viterbi.h
    src/param.cpp
    src/tokenizer.cpp
    src/ucstable.h
    src/char_property.cpp
    src/dictionary.h
    src/scoped_ptr.h
    src/param.h
    src/mecab.h
    src/dictionary.cpp
    src/feature_index.cpp
    src/feature_index.h
    src/lbfgs.cpp
    src/lbfgs.h
    src/learner_tagger.cpp
    src/learner_tagger.h
    src/learner.cpp
    src/learner_node.h
    src/libmecab.cpp
    java/MeCab_wrap.cxx
)

include_directories(
    src/
)

add_definitions(
    -DDIC_VERSION=102
    -DHAVE_DIRENT_H
    -DHAVE_FCNTL_H
    -DHAVE_STDINT_H
    -DHAVE_SYS_STAT_H
    -DHAVE_SYS_TYPES_H
    -DHAVE_UNISTD_H
    -DMECAB_DEFAULT_RC=""
    -DPACKAGE="mecab"
    -DVERSION="0.996"
)

target_compile_options(mecab PRIVATE -Wno-deprecated-register)
