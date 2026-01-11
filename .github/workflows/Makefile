# Sonic 1 Forever WASM Makefile
CC = em++

# Game logic flags: Enable SDL2, Touch Controls for mobile, and Haptics (vibration)
CXXFLAGS = -O3 -std=c++11 -DRETRO_USING_SDL2 -DRETRO_TOUCH_CONTROLS -DRETRO_USE_HAPTICS -DRETRO_USE_NETWORKING

# Emscripten specific flags to turn C++ into a Website
EM_FLAGS = -s WASM=1 \
           -s USE_SDL=2 \
           -s USE_SDL_MIXER=2 \
           -s USE_OGG=1 \
           -s USE_VORBIS=1 \
           -s ALLOW_MEMORY_GROWTH=1 \
           -s NO_EXIT_RUNTIME=1 \
           -s "EXPORTED_RUNTIME_METHODS=['ccall']" \
           --shell-file shell_minimal.html

# This finds all the Sonic engine code files automatically
SOURCES = $(wildcard RSDKv4/*.cpp) $(wildcard RSDKv4/main/*.cpp) $(wildcard RSDKv4/S3/*.cpp)

all:
	$(CC) $(SOURCES) $(CXXFLAGS) $(EM_FLAGS) -o index.html
