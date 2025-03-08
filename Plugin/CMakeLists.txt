cmake_minimum_required(VERSION 3.30.5)

Project(Plugin VERSION 0.1.0)

juce_add_plugin(${PROJECT_NAME}
        COMPANY_NAME Alex Fortunato Music
        IS_SYNTH FALSE
        NEEDS_MIDI_INPUT FALSE
        NEEDS_MIDI_OUTPUT FALSE
        PLUGIN_MANUFACTURER_CODE
        PLUGIN_CODE
        FORMATS VST3 Standalone
        PRODUCT_NAME "Plugin Name"
)

target_sources(${PROJECT_NAME}
        PRIVATE
        Source/PluginEditor.cpp
        Source/PluginProcessor.cpp
        Source/PluginEditor.h
        Source/PluginProcessor.h
)


target_link_libraries(${PROJECT_NAME}
        PRIVATE
        juce::juce_audio_utils
        PUBLIC
        juce::juce_recommended_config_flags
        juce::juce_recommended_lto_flags
        juce::juce_recommended_warning_flags
)

target_compile_definitions(${PROJECT_NAME}
        PUBLIC
        JUCE_WEB_BROWSER=0
        JUCE_UCE_CURL=0
        JUCE_VST3_CAN_REPLACE_VST2=0
)