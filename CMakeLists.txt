cmake_minimum_required(VERSION 3.5)

set(CMAKE_CXX_STANDARD 11)

add_library(machineid STATIC src/machineid/machineid.cpp)
target_include_directories(machineid
	PRIVATE src
	PUBLIC include)
if (WIN32)
	target_link_libraries(machineid
        	iphlpapi.lib
        	)
else()
	target_link_libraries(machineid)
endif()
