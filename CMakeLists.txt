cmake_minimum_required(VERSION 3.10)
project(WEB-AGENT)

# Указываем компилятору искать заголовочные файлы в текущей директории
include_directories(${CMAKE_CURRENT_SOURCE_DIR})

# Добавляем зависимость на nlohmann/json (если используете)
find_package(nlohmann_json REQUIRED)
include_directories(lib/inih)

# Исходные файлы проекта
set(SOURCES
    src/agent.cpp
    lib/inih/ini.c
)

add_executable(web_agent ${SOURCES})

# Связываем с библиотекой nlohmann_json
target_link_libraries(web_agent nlohmann_json::nlohmann_json)
