cmake_minimum_required(VERSION 3.13)

project(SpoutSDK VERSION 2.006
	DESCRIPTION "Spout2 SDK Library"
	LANGUAGES CXX)

# project-wide c++ standard settings
set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

# CMake related options for this project
set(CMAKE_MODULE_PATH "${PROJECT_SOURCE_DIR}/cmake" ${CMAKE_MODULE_PATH})
	
# build render app
add_library(Spout2 STATIC "")
target_sources(Spout2
	PRIVATE
		SpoutCopy.cpp
		SpoutDirectX.cpp
		SpoutGLDXinterop.cpp
		SpoutGLextensions.cpp
		SpoutMemoryShare.cpp
		SpoutReceiver.cpp
		SpoutSDK.cpp
		SpoutSender.cpp
		SpoutSenderMemory.cpp
		SpoutSenderNames.cpp
		SpoutSharedMemory.cpp
	PUBLIC
		Spout.h
		SpoutCommon.h
		SpoutCopy.h
		SpoutDirectX.h
		SpoutGLDXinterop.h
		SpoutGLextensions.h
		SpoutMemoryShare.h
		SpoutReceiver.h
		SpoutSDK.h
		SpoutSender.h
		SpoutSenderMemory.h
		SpoutSenderNames.h
		SpoutSharedMemory.h

)
target_include_directories(Spout2 PUBLIC ${CMAKE_CURRENT_LIST_DIR}/)

