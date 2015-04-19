# machine

cmake_minimum_required(VERSION 3.0)


FIND_PACKAGE(FLEX REQUIRED)

#SET(FlexOutput ${CMAKE_SOURCE_DIR}/machine/uscan.cpp})
# IF(FLEX_FOUND)
     # ADD_CUSTOM_COMMAND(
       # SOURCE ${CMAKE_SOURCE_DIR}/machine/uscan.l
       # COMMAND ${FLEX_EXECUTABLE}
				 # --outfile=${FlexOutput}
            # ${CMAKE_SOURCE_DIR}/machine/uscan.l
			# --lfl
       # COMMENT "Generating scanner.cpp"
     # )
# ENDIF()

#FLEX_TARGET(flexer uscan.l ${CMAKE_SOURCE_DIR}/uscan.cpp -lfl)

FILE(GLOB UMACHINE_HEADERS *.h)
FILE(GLOB UMACHINE_SOURCES *.c)
FILE(GLOB UMACHINE_SOURCES *.cpp)

#add_library(flexer)
add_library( machine STATIC ${UMACHINE_HEADERS} ${UMACHINEC_SOURCES} ${UMACHINE_SOURCES})

install(TARGETS machine DESTINATION lib)
install( FILES UMACHINE_HEADERS DESTINATION include)


include_directories(${CMAKE_CURRENT_SOURCE_DIR})
include_directories(${CMAKE_CURRENT_BINARY_DIR})

source_group(Headers FILES ${UMACHINE_HEADERS})
source_group(Sources FILES ${UMACHINE_SOURCES})
source_group(Sources FILES ${UMACHINEC_SOURCES})

