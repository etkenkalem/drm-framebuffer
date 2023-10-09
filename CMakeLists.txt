cmake_minimum_required(VERSION 3.1)

project(drmbuffer)

include_directories(.)



find_package(PkgConfig REQUIRED)
pkg_check_modules(LIBDRM REQUIRED IMPORTED_TARGET libdrm)

message("DRM INCLUDE DIRS ${LIBDRM_INCLUDE_DIRS}")
include_directories(${LIBDRM_INCLUDE_DIRS})
#add_library(FFmpeg INTERFACE IMPORTED GLOBAL)



add_executable(${PROJECT_NAME} main.c framebuffer.c)
target_link_libraries(${PROJECT_NAME}  drm)

#target_link_libraries(${PROJECT_NAME} pkgConfig::SWSCALE)


#target_link_libraries(${PROJECT_NAME}  "-llibdrm")
