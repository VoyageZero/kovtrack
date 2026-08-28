cmake_minimum_required(VERSION 3.20)

project(
  kovtrack 
  VERSION 0.1.0
  DESCRIPTION "Aim analyzer tool for Kovaak's Aim Trainer."
  LANGUAGES CXX
)

find_package(nlohmann_json CONFIG REQUIRED)
find_package(protobuf CONFIG REQUIRED)

add_executable(${CMAKE_PROJECT_NAME})

target_sources(
  ${CMAKE_PROJECT_NAME}
  PRIVATE
    src/main.cpp
)

target_include_directories(${CMAKE_PROJECT_NAME} PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/include)

target_link_libraries(${CMAKE_PROJECT_NAME} 
  PRIVATE 
    nlohmann_json::nlohmann_json
    protobuf::libprotobuf
)

# Uncomment when needed
# protobuf_generate(
#  LANGUAGE CPP 
#  TARGET ${CMAKE_PROJECT_NAME}
#  PROTOS ${CMAKE_CURRENT_SOURCE_DIR}/proto/performance.proto
#)

target_include_directories(${CMAKE_PROJECT_NAME} PRIVATE ${CMAKE_CURRENT_BINARY_DIR})
