add_executable(a.out main.cpp)

find_package(OpenSSL REQUIRED)
message(STATUS "OpenSSL_INCLUDE_DIR: ${OPENSSL_INCLUDE_DIR}")

find_package(Boost REQUIRED COMPONENTS system)
message(STATUS "Boost_INCLUDE_DIRS: ${Boost_INCLUDE_DIRS}")

target_include_directories(a.out PRIVATE ${CMAKE_SOURCE_DIR}/websocketpp)
target_link_libraries(a.out PRIVATE Boost::system ${OPENSSL_LIBRARIES})
