cmake_minimum_required(VERSION 3.16)
project(SimpleFFTTutorial)

set(CMAKE_OSX_ARCHITECTURES "arm64" CACHE STRING "Build architecture" FORCE)
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_subdirectory("../JUCE" JUCE)
add_subdirectory("../CustomMatPlot" CustomMatPlot)

add_executable(SimpleFFTTutorial Source/Main.cpp)

set(JUCE_MODULES 
    juce::juce_gui_basics
    juce::juce_audio_basics
    juce::juce_audio_devices
    juce::juce_audio_formats
    juce::juce_audio_processors
    juce::juce_audio_utils
    juce::juce_dsp)

target_link_libraries(SimpleFFTTutorial PRIVATE cmp_plot ${JUCE_MODULES})
target_include_directories(SimpleFFTTutorial PRIVATE JuceLibraryCode)
target_include_directories(SimpleFFTTutorial PRIVATE ../CustomMatPlot/include/include
                                                      ${CMAKE_CURRENT_BINARY_DIR}/CustomMatPlot/include/include)