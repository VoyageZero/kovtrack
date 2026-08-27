cmake_minimum_required(VERSION 3.20)

project(
  kovtrack 
  VERSION 0.1.0
  DESCRIPTION "Aim analyzer tool for Kovaak's Aim Trainer."
  LANGUAGES CXX
)

add_executable(${CMAKE_PROJECT_NAME})

target_sources(
  ${CMAKE_PROJECT_NAME}
  PRIVATE
    src/main.cpp
)
