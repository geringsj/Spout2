# adapted from https://rix0r.nl/blog/2015/08/13/cmake-guide/

cmake_minimum_required(VERSION 3.13)

project(Spout VERSION 2.006
	DESCRIPTION "Spout2 is a video frame sharing system for Microsoft Windows"
	LANGUAGES CXX)
	
# include libraries?

# add sub-projects
add_subdirectory(SpoutSDK/Source)
