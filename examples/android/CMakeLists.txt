cmake_minimum_required(VERSION 3.22)
project(llama-android)

set(CMAKE_CXX_STANDARD 17)
set(LLAMA_VULKAN ON)
set(LLAMA_VULKAN_F16 ON)

# Path to your llama.cpp sources
file(GLOB_RECURSE LLAMA_SRC "../../*.cpp" "../../*.h")

add_library(llama-lib SHARED ${LLAMA_SRC})
find_library(log-lib log)
target_link_libraries(llama-lib ${log-lib})
