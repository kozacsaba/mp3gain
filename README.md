# mp3gain

-----

* The original project was a standalone program / dynamic library that I couldn't manage to fit my needs. I turned it into a submodule that can be used in your projects with CMake.
* Make sure to add `${MP3GAIN_SOURCE_DIR}/mp3gain` to your include directories, link the `mp3gain` library to your target, and you should be good to go.
* Only used `int changeGain(char *filename, int leftgainchange, int rightgainchange);` from `mp3gain.h` so far, not sure about other funcitons.
* This is optional, but I also use `target_compile_definitions(mp3gain PUBLIC MP3GAIN_SILENT)` instead of going through every deprication warning or unique solution that is used on the original project.

-----

This project is not yet Mac-compatible, because I do not have a Mac to develop on. If you would like to make this work on Mac, feel free to contribute.
