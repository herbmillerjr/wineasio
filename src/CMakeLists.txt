cmake_minimum_required(VERSION 3.13)
project(wineasio_objects C)

set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -O2 -D__WINESRC__ -D_REENTRANT -fPIC -Wall -pipe -fno-strict-aliasing -Wdeclaration-after-statement -Wwrite-strings -Wpointer-arith")
if(NOT WIN64)
	set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -m32")
endif()

include_directories(${WINE_INCLUDE_PATH} ${WINE_INCLUDE_PATH}/windows)

add_library(interim OBJECT asio.c main.c regsvr.c)
