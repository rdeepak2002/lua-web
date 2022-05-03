## About

This is an emscripten compiled version of Lua 5.3.6.

## How to Build Lua for Emscripten / Web Assembly

Run the following command in the deeps-engine-latest/src/engine/external/lua-5.3.6/src folder:

```shell
make generic CC='emcc -s WASM=1' AR='emar rcu' RANLIB='emranlib'
```

Link as library for emscripten using cmake:

```cmake
if (${CMAKE_SYSTEM_NAME} MATCHES "Emscripten")
  set_target_properties(${PROJECT_NAME} PROPERTIES LINK_FLAGS "... -L${PROJECT_SOURCE_DIR}/lua-web/src -s ...")
endif ()
```
