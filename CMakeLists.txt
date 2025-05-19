cmake_minimum_required(VERSION 3.13 FATAL_ERROR)

# Устанавливаем имя проекта в переменную
set(PROJECT_NAME_SNAKE snake)

# Устанавливаем имя проекта
project(${PROJECT_NAME_SNAKE})

# Добавляем исполняемый файл
add_executable(${PROJECT_NAME_SNAKE} main.cpp)

# Настройки для сборки GLFW
set(GLFW_BUILD_DOCS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)
set(GLFW_INSTALL OFF CACHE BOOL "" FORCE)

# Подключаем GLFW (путь должен быть корректным!)
add_subdirectory(external/glfw)

# Линкуем GLFW к нашему исполняемому файлу
target_link_libraries(${PROJECT_NAME_SNAKE} glfw)
