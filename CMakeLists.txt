cmake_minimum_required(VERSION 3.2)
project(super-build-example)

include(ExternalProject)

ExternalProject_Add(
    x
    URL https://github.com/cgold-examples/x/archive/v1.0.tar.gz
    URL_HASH SHA1=3c15777fddee4fbf41a57241effc59a821562f65
    CMAKE_ARGS -DCMAKE_INSTALL_PREFIX=${CMAKE_INSTALL_PREFIX}
)

ExternalProject_Add(
    a
    URL https://github.com/cgold-examples/a/archive/v1.0.tar.gz
    URL_HASH SHA1=9adb3574369cf3c186b4984eb6778fca5866e347
    CMAKE_ARGS -DCMAKE_INSTALL_PREFIX=${CMAKE_INSTALL_PREFIX}
    DEPENDS x
)

ExternalProject_Add(
    b
    URL https://github.com/cgold-examples/b/archive/v1.0.tar.gz
    URL_HASH SHA1=7ef127ddc31d6a9b510d9cdc318c68c7709a8204
    CMAKE_ARGS -DCMAKE_INSTALL_PREFIX=${CMAKE_INSTALL_PREFIX}
    DEPENDS x
)
