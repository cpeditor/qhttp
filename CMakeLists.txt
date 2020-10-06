cmake_minimum_required(VERSION 3.5)

project(QHttp)

set(CMAKE_CXX_STANDARD 14)

find_package(Qt5 COMPONENTS Network REQUIRED)

add_library(QHttp STATIC 
    src/qhttpclient.cpp
    src/qhttpabstracts.cpp
    src/qhttpabstracts.hpp
    src/qhttpclient.hpp
    src/qhttpclientrequest.cpp
    src/qhttpclientrequest.hpp
    src/qhttpclientresponse.cpp
    src/qhttpclientresponse.hpp
    src/qhttpfwd.hpp
    src/qhttpserver.cpp
    src/qhttpserver.hpp
    src/qhttpserverconnection.cpp
    src/qhttpserverconnection.hpp
    src/qhttpserverrequest.cpp
    src/qhttpserverrequest.hpp
    src/qhttpserverresponse.cpp
    src/qhttpserverresponse.hpp
    
    src/private/httpparser.hxx
    src/private/httpreader.hxx
    src/private/httpwriter.hxx
    src/private/qhttpbase.hpp
    src/private/qhttpclient_private.hpp
    src/private/qhttpclientrequest_private.hpp
    src/private/qhttpclientresponse_private.hpp
    src/private/qhttpserver_private.hpp
    src/private/qhttpserverconnection_private.hpp
    src/private/qhttpserverrequest_private.hpp
    src/private/qhttpserverresponse_private.hpp
    src/private/qsocket.hpp

    3rdparty/http-parser/http_parser.c
    3rdparty/http-parser/http_parser.h

)

target_include_directories(QHttp PUBLIC src)
target_link_libraries(QHttp PRIVATE Qt5::Network)
