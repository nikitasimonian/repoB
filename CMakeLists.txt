cmake_minimum_required(VERSION 3.21)
project(B)

if (NOT TARGET ${PROJECT_NAME})
    add_library(${PROJECT_NAME} STATIC)
    target_sources(${PROJECT_NAME} PUBLIC
        ${CMAKE_CURRENT_SOURCE_DIR}/${PROJECT_NAME}/b.h
        ${CMAKE_CURRENT_SOURCE_DIR}/${PROJECT_NAME}/b.cpp
    )
    target_include_directories(${PROJECT_NAME} INTERFACE ${CMAKE_CURRENT_SOURCE_DIR})
    target_include_directories(${PROJECT_NAME} PUBLIC $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}>)
endif()