cmake_minimum_required(VERSION 2.8)

project(app_project)
set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} ${PROJECT_SOURCE_DIR}/CMake)
SET(GRAVIT_INSTALL_DIR /home/users/applekey/documents/gravit/install/lib)
SET(GRAVIT_SOURCE_DIR /home/users/applekey/documents/gravit/src)

find_package(Boost REQUIRED COMPONENTS system)
find_package(TBB REQUIRED)
find_package(MPI REQUIRED)
find_package(Embree REQUIRED)

INCLUDE_DIRECTORIES(

${TBB_INCLUDE_DIRS}
${Boost_INCLUDE_DIRS}
${MPI_INCLUDE_PATH}
${GRAVIT_SOURCE_DIR}
)
add_executable(my run.cpp)
TARGET_LINK_LIBRARIES(my   ${GRAVIT_INSTALL_DIR}/libAPICode.a   ${GRAVIT_INSTALL_DIR}/libgvtCore.a  ${GRAVIT_INSTALL_DIR}/libgvtRender.a  ${Boost_LIBRARIES} ${TBB_LIBRARIES} ${MPI_LIBRARIES} ${EMBREE_TARGET_LINK_LIBRARIES})
