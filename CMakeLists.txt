cmake_minimum_required(VERSION 3.16)
project(SimpleFFTTutorial)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Add JUCE subdirectory
add_subdirectory("../../Desktop/coding for fun/JUCE" JUCE)

add_subdirectory("../../Desktop/coding for fun/CustomMatPlot" CustomMatPlot)

add_executable(SimpleFFTTutorial Source/Main.cpp)
target_link_libraries(SimpleFFTTutorial CustomMatPlot juce::juce_gui_basics)