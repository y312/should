CMAKE_MINIMUM_REQUIRED(VERSION 2.6)

SET(SHOULD_SRCS should.c)
SET(SHOULD_HEADERS should.h)

ADD_LIBRARY(should SHARED ${SHOULD_SRCS})

SET(SHOULD_VERSION_MAJOR 0)
SET(SHOULD_VERSION_MINOR 8)
SET(SHOULD_VERSION_PATCH 0)
SET(SHOULD_VERSION_STRING 
    ${SHOULD_VERSION_MAJOR}.${SHOULD_VERSION_MINOR}.${SHOULD_VERSION_PATCH}
    )

SET_TARGET_PROPERTIES(should PROPERTIES
    VERSION ${SHOULD_VERSION_STRING}
    SOVERSION ${SHOULD_VERSION_MAJOR}
    )

INSTALL(TARGETS should
    LIBRARY DESTINATION lib
    ARCHIVE DESTINATION lib
    )

INSTALL(FILES ${SHOULD_HEADERS} DESTINATION "include/should")
