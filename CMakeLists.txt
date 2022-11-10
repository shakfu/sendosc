cmake_minimum_required(VERSION 3.1)

project(sendosc)

set (CMAKE_CXX_STANDARD 11)

set(OSC ${CMAKE_SOURCE_DIR}/src/osc)
set(IP  ${CMAKE_SOURCE_DIR}/src/ip)

set(CMAKE_CXX_FLAGS "-g -Wall")
set(CMAKE_C_FLAGS "-g -Wall")

set (SOURCES
    ${OSC}/OscTypes.cpp
    ${OSC}/OscOutboundPacketStream.cpp
    ${OSC}/OscReceivedElements.cpp
    ${OSC}/OscPrintReceivedElements.cpp
    ${IP}/posix/UdpSocket.cpp
    ${IP}/IpEndpointName.cpp
    ${IP}/posix/NetworkingUtils.cpp
)

include_directories(${CMAKE_SOURCE_DIR}/src)

add_library(oscpack STATIC ${SOURCES})

add_executable(sendosc src/sendosc.cpp)

target_link_libraries(sendosc oscpack)
