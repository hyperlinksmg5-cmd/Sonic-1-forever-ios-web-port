# Sonic 1 Forever WASM Makefile
CC = em++

# These flags tell the compiler to turn on Touch Controls and use Web libraries
CXXFLAGS = -O3 -std=c++11 -DRETRO_USING_SDL2 -DRETRO_TOUCH_CONTROLS -DRETRO_USE_HAPTICS

# Emscripten specific settings
EM_FLAGS = -s WASM=1 \
           -s USE_SDL=2 \
           -s USE_SDL_MIXER=2 \
           -s USE_OGG=1 \
           -s USE_VORBIS=1 \
           -s ALLOW_MEMORY_GROWTH=1 \
           -s NO_EXIT_RUNTIME=1 \
           -s "EXPORTED_RUNTIME_METHODS=['ccall']" \
           --shell-file shell_minimal.html

# This automatically finds all your .cpp files so you don't have to list them one by one
SOURCES = $(wildcard RSDKv4/*.cpp) $(wildcard RSDKv4/main/*.cpp)

all:
	$(CC) $(SOURCES) $(CXXFLAGS) $(EM_FLAGS) -o index.html
