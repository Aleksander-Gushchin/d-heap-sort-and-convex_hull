﻿cmake_minimum_required(VERSION 2.8) #Проверка версии CMake.

set(PROJECT_NAME ADA) #Создаем обычную локальную переменную с именем проекта
project(${PROJECT_NAME}) # Название проекта

set(convex_hull_main convex_hull_main) #Переменная с именем библиотеки
set(convex_hull_lib convex_hull_lib) #Переменная с именем библиотеки
set(d_heap_sort_main d_heap_sort_main)
set(d_heap_sort_lib d_heap_sort_lib)

set(CMAKE_CONFIGURATION_TYPES "Debug;Release" CACHE STRING "Configs" FORCE) #Создается переменная CMAKE_CONFIGURATION_TYPES со значением "Debug;Release" и меткой/разделом Configs, переменная сохраниется в специальном файле доступном из всех файлов,
if(NOT CMAKE_BUILD_TYPE) # проверка имеющихся у компилятора вариантов сборки
  set(CMAKE_BUILD_TYPE Release) #Если нет то устанавливаем Release
endif()

include_directories(
 ${CMAKE_CURRENT_SOURCE_DIR}/convex_hull_lib
 ${CMAKE_CURRENT_SOURCE_DIR}/d_heap_sort_lib)


add_subdirectory(convex_hull_main)
add_subdirectory(convex_hull_lib)
add_subdirectory(d_heap_sort_main)
add_subdirectory(d_heap_sort_lib)


