cmake_minimum_required(VERSION 4.1)

cmake_policy(SET CMP0181 NEW)

project(dsc-miner C CXX)

set(FAST_CISH_FLAGS -O3)
set(FAST_CFLAGS ${FAST_CISH_FLAGS} ${COLOR_DIAGS} -fvectorize -flto=full -fvisibility=hidden -fvisibility-inlines-hidden -fvisibility-inlines-hidden-static-local-var -fdata-sections -ffunction-sections -march=native)
set(FAST_CXXFLAGS ${FAST_CFLAGS})
set(FAST_LDFLAGS ${FAST_CXXFLAGS})

add_compile_options(${FAST_CXXFLAGS})
add_link_options(${FAST_LDFLAGS})

# add_compile_options(-fsanitize=address -fno-omit-frame-pointer -g -O0)
# add_link_options(-fsanitize=address -O0)

set(CMAKE_CXX_STANDARD 23)

add_subdirectory(3rdparty)
add_subdirectory(lib)
add_subdirectory(tools)
