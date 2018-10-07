include(ExternalProject)

set(SDK_INSTALL_PREFIX ${CMAKE_BINARY_DIR}/sdk)

ExternalProject_Add(
        SquirrelLang_project
        #URL ${CMAKE_CURRENT_SOURCE_DIR}/squirrel
        GIT_REPOSITORY https://github.com/sim82/squirrel.git
        GIT_TAG master

        CMAKE_ARGS
            -DCMAKE_BUILD_TYPE=$<CONFIG>
            -DBUILD_SHARED_LIBS=${BUILD_SHARED_LIBS}
            -DCMAKE_INSTALL_RPATH=${SDK_INSTALL_PREFIX}/lib64
            -DCMAKE_INSTALL_PREFIX:PATH=${SDK_INSTALL_PREFIX}
)
ExternalProject_Add(
        Zlib_project
        GIT_REPOSITORY https://github.com/sim82/zlib.git
        GIT_TAG master

        CMAKE_ARGS
            -DCMAKE_BUILD_TYPE=$<CONFIG>
            -DBUILD_SHARED_LIBS=${BUILD_SHARED_LIBS}
            -DCMAKE_INSTALL_RPATH=${SDK_INSTALL_PREFIX}/lib64
            -DCMAKE_INSTALL_PREFIX:PATH=${SDK_INSTALL_PREFIX}
)
ExternalProject_Add(
        Libpng_project
        GIT_REPOSITORY https://github.com/sim82/libpng.git
        GIT_TAG master

        CMAKE_ARGS
            -DCMAKE_BUILD_TYPE=$<CONFIG>
            -DBUILD_SHARED_LIBS=${BUILD_SHARED_LIBS}
            -DCMAKE_INSTALL_RPATH=${SDK_INSTALL_PREFIX}/lib64
            -DCMAKE_INSTALL_PREFIX:PATH=${SDK_INSTALL_PREFIX}
)
ExternalProject_Add(
        Freetype_project
        GIT_REPOSITORY https://github.com/sim82/freetype2.git
        GIT_TAG master

        CMAKE_ARGS
            -DCMAKE_BUILD_TYPE=$<CONFIG>
            -DBUILD_SHARED_LIBS=${BUILD_SHARED_LIBS}
            -DCMAKE_INSTALL_RPATH=${SDK_INSTALL_PREFIX}/lib64
            -DCMAKE_INSTALL_PREFIX:PATH=${SDK_INSTALL_PREFIX}
)
ExternalProject_Add(
        Turbojpeg_project
        GIT_REPOSITORY https://github.com/sim82/libjpeg-turbo.git
        GIT_TAG master

        CMAKE_ARGS
            -DCMAKE_BUILD_TYPE=$<CONFIG>
            -DBUILD_SHARED_LIBS=${BUILD_SHARED_LIBS}
            -DCMAKE_INSTALL_RPATH=${SDK_INSTALL_PREFIX}/lib64
            -DCMAKE_INSTALL_PREFIX:PATH=${SDK_INSTALL_PREFIX}
)

ExternalProject_Add(
        CapNProto_project
        #URL ${CMAKE_SOURCE_DIR}/squirrel
        GIT_REPOSITORY https://github.com/capnproto/capnproto.git

        GIT_TAG v0.7.0
        URL ${CMAKE_CURRENT_SOURCE_DIR}/capnproto/c++

        CMAKE_ARGS
            -DCMAKE_INSTALL_RPATH=${SDK_INSTALL_PREFIX}/lib64
            -DCMAKE_BUILD_TYPE=$<CONFIG>
            -DCMAKE_C_COMPILER=${CMAKE_C_COMPILER}
            -DCMAKE_CXX_COMPILER=${CMAKE_CXX_COMPILER}
            -DMSVC=${MSVC}
            -DBUILD_SHARED_LIBS=${BUILD_SHARED_LIBS}
            -DCMAKE_INSTALL_PREFIX:PATH=${SDK_INSTALL_PREFIX} 
            -DBUILD_TESTING=False
)


