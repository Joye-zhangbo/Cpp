# CMake��Ͱ汾Ҫ��
cmake_minimum_required(VERSION 2.8.3)

# Compile as C++11
add_compile_options(-std=c++11)

# ��Ŀ��Ϣ
PROJECT(boost_thread)
 
# ���Ұ�, opencvʹ��
find_package(Boost REQUIRED COMPONENTS system thread)

# ����ͷ�ļ�·��
include_directories(${Boost_INCLUDE_DIRS} ${CMAKE_CURRENT_LIST_DIR}/include)

# ָ������Ŀ�꣬����source_path����
add_executable(mutex      src/mutex.cpp)
# Ŀ�����ӿ�
target_link_libraries(mutex      ${Boost_LIBRARIES})

# ָ������Ŀ�꣬����source_path����
add_executable(lock_guard      src/lock_guard.cpp)
# Ŀ�����ӿ�
target_link_libraries(lock_guard      ${Boost_LIBRARIES})

# ָ������Ŀ�꣬����source_path����
add_executable(unique_lock      src/unique_lock.cpp)
# Ŀ�����ӿ�
target_link_libraries(unique_lock      ${Boost_LIBRARIES})

# ָ������Ŀ�꣬����source_path����
add_executable(shared_lock      src/shared_lock.cpp)
# Ŀ�����ӿ�
target_link_libraries(shared_lock      ${Boost_LIBRARIES})

# ָ������Ŀ�꣬����source_path����
add_executable(unique_lock_mutex      src/unique_lock_mutex.cpp)
# Ŀ�����ӿ�
target_link_libraries(unique_lock_mutex      ${Boost_LIBRARIES})

# ָ������Ŀ�꣬����source_path����
add_executable(thread_local_storage      src/thread_local_storage.cpp)
# Ŀ�����ӿ�
target_link_libraries(thread_local_storage      ${Boost_LIBRARIES})

# ��ʽָ��������
set(CMAKE_CXX_COMPILER "g++") 
# ����������Ϣ
set(CMAKE_BUILD_TYPE "Debug")
set(CMAKE_CXX_FLAGS_DEBUG "$ENV{CXXFLAGS} -O0 -Wall -g2 -ggdb")
set(CMAKE_CXX_FLAGS_RELEASE "$ENV{CXXFLAGS} -O3 -Wall")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -g")
# �������о���
set(CMAKE_CXX_FLAGS "-Wall")
 