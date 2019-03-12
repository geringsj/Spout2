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

# OpenGL
find_package(OpenGL REQUIRED)

set(LINK_LIBS_EXTERNAL ${OPENGL_gl_LIBRARY} ${OPENGL_glu_LIBRARY})
set(INCLUDE_LIBS_EXTERNAL ${OPENGL_INCLUDE_DIR})

# build render app
add_library(Spout2  
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
target_include_directories(Spout2 PUBLIC
    $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/>
    $<INSTALL_INTERFACE:./>
    PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/ ${INCLUDE_LIBS_EXTERNAL})
	
target_link_libraries(Spout2 PRIVATE ${LINK_LIBS_EXTERNAL})
