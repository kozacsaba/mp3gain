# mp3gain ######################################################################

cmake_minimum_required(VERSION 3.22)
project("mp3gain" VERSION 1.0)

add_library(mp3gain STATIC
    mp3gain/mp3gain.c
    mp3gain/apetag.c
    mp3gain/rg_error.c
    mp3gain/gain_analysis.c
    mp3gain/id3tag.c
    #${MP3SRC}/replaygaindll.c

    mp3gain/mpglibDBL/common.c
    mp3gain/mpglibDBL/dct64_i386.c
    mp3gain/mpglibDBL/decode_i386.c
    mp3gain/mpglibDBL/interface.c
    mp3gain/mpglibDBL/layer1.c
    mp3gain/mpglibDBL/layer2.c
    mp3gain/mpglibDBL/layer3.c
    mp3gain/mpglibDBL/tabinit.c
)

if(MSVC)
    target_compile_options(mp3gain PRIVATE /w)
else()
    target_compile_options(mp3gain PRIVATE -w)
endif()

# this should not always have WIN32 defined, only on windows

target_compile_definitions(mp3gain PUBLIC
    HAVE_MEMCPY
    WIN32
)

target_include_directories(mp3gain PUBLIC
    mp3gain
)
